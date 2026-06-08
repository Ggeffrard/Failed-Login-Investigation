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

# Retrieve login attempts on specific dates

I queried the login activity database to retrieve all login attempts that occurred on May 8, 2022, and May 9, 2022. This allowed me to examine authentication activity before and during the reported security event to identify any unusual patterns or indicators of compromise.

The command to complete this step:

SELECT * 

FROM log_in_attempts 

WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';

<img width="1113" height="927" alt="Screenshot 2026-06-08 095823" src="https://github.com/user-attachments/assets/277099a0-3528-487e-b8a4-26d269100530" />
<img width="1157" height="965" alt="Screenshot 2026-06-08 095853" src="https://github.com/user-attachments/assets/e963bc42-3b97-4996-89aa-05a9cdd254de" />
<img width="1177" height="137" alt="Screenshot 2026-06-08 095943" src="https://github.com/user-attachments/assets/b1862657-1886-4862-95c7-b9f754c3d628" />

There are 75 login attempts in these two days.

# Retrieve login attempts outside of Mexico

I analyzed authentication records to identify login attempts that originated outside of Mexico. Using SQL’s NOT and LIKE operators, I filtered out records associated with locations matching the pattern “MEX%”, allowing me to focus on login activity from other countries. This helped identify potentially unusual access attempts originating from outside the expected geographic region.

The command to complete this step:

SELECT * 

FROM log_in_attempts 

WHERE NOT country LIKE 'MEX%';

<img width="611" height="125" alt="Screenshot 2026-06-08 100056" src="https://github.com/user-attachments/assets/07e0a82a-81df-4e83-bc6d-817ff8264312" />
<img width="992" height="868" alt="Screenshot 2026-06-08 100128" src="https://github.com/user-attachments/assets/92e55ac7-fa14-49b9-8b14-ddb1be9063ad" />
<img width="1005" height="952" alt="Screenshot 2026-06-08 100314" src="https://github.com/user-attachments/assets/0fbae8ce-719e-4311-a881-18a570f74dd0" />
<img width="1041" height="958" alt="Screenshot 2026-06-08 100340" src="https://github.com/user-attachments/assets/7c56d60d-3c23-4a9e-a839-5efa4674b014" />
<img width="1132" height="788" alt="Screenshot 2026-06-08 100403" src="https://github.com/user-attachments/assets/7cddcb6f-16a2-46aa-8380-dff0be5a07ed" />

There are 144 login attempts made outside of Mexico.



