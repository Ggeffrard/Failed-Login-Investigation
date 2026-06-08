# Failed Login Investigation 

## Project Overview

This project demonstrates how SQL can be used to investigate authentication logs and identify failed login attempts that may indicate unauthorized access attempts or suspicious user activity.

## Project Objective

The objective of this project was to analyze login attempt records using SQL queries to identify failed authentication attempts, investigate suspicious activity, and gain hands-on experience performing security investigations using database analysis techniques.

## Technologies Used

- SQL
- MariaDB
- Linux
- Security Logs

  # Retrieve after hours failed login attempts
  
I examined login activity records to locate unsuccessful login attempts that occurred after normal business hours. Using SQL filters, I narrowed the results to login events that took place after 18:00 and were marked as failed. This helped isolate potentially suspicious authentication activity for further review.

The command to complete this step:

SELECT *

FROM log_in_attempts

WHERE login_time > '18:00' AND success = FALSE;

<img width="772" height="108" alt="Screenshot 2026-06-08 101538" src="https://github.com/user-attachments/assets/9428723c-bd17-4bd5-b3f1-fe2575d748a5" />
<img width="1897" height="911" alt="Screenshot 2026-06-08 095726" src="https://github.com/user-attachments/assets/9db60738-2488-4324-aad9-a30a901ced8e" />

There are 19 failed login attempts that occurred after 18:00.


