function onChange(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  
  // Check if the change type is 'INSERT_ROW'
  if (e.changeType === 'INSERT_ROW') {
    var lastRow = sheet.getLastRow(); // Assuming the new row is the last one
    
    // Example to set datestamp and timestamp on the new row
    var dateStampCell = sheet.getRange(lastRow, 15); // Assuming column 15 is the datestamp column
    var timeCell = sheet.getRange(lastRow, 16); // Assuming column 16 is the time column
    dateStampCell.setValue(new Date()).setNumberFormat("yyyy-MM-dd");
    timeCell.setValue(new Date()).setNumberFormat("HH:mm:ss");

    // Send notification to HR about the new hire
    sendHRNotification(sheet, lastRow);
  }
}

function sendHRNotification(sheet, row) {
  var rowData = sheet.getRange(row, 1, 1, 14).getValues()[0];
  var employeeName = rowData[0]; // Assuming the employee's first name is in Column A
  var emailAddress = 'amohammed@meadowb.com'; // HR's email address, for testing purposes
  var subject = 'Action Required: New Employee Setup';
  var body = `<p>Hello,</p>
              <p>A new employee named <strong>${employeeName}</strong> has been added to the system. Please review their details and specify the necessary items and access they require.</p>
              <p>You can enter the required items in the following document: <a href="https://docs.google.com/spreadsheets/d/1b0VKjDs0nFkFcEL94M0xVxp2uP0_h__3G0zhXZoDaN4/edit#gid=0">Employee Setup Sheet</a>.</p>
              <p>Please ensure this is completed as soon as possible to facilitate a smooth onboarding process.</p>
              <p>Thank you,</p>
              <p>MeadowBrook Construction Team</p>`;

  MailApp.sendEmail({
    to: emailAddress,
    subject: subject,
    htmlBody: body
  });

  Logger.log('Notification email sent to HR: ' + emailAddress);
}

// Set up the onChange trigger manually in the Google Script editor under Triggers
