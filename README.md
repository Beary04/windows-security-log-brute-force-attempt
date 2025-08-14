# windows-security-log-brute-force-attempt
A hands-on Splunk lab demonstrating the ingestion and analysis of Windows Security logs. The lab showcases event types such as password resets (4724), account changes (4738), and failed logons (4625), highlighting practical skills in log management, event auditing, and Splunk search queries. This lab shows a potential brute force attack under way with an alarming amount of failed logon attempts.  


# Splunk Security Event Lab

## Objective
Demonstrate ingestion and analysis of Windows Security logs in Splunk, highlighting key events like password failed logons (4625), account changes (4738), and successful logons (4624).

## Tools Used
- Splunk Enterprise (host)
- Windows 10 VM (source of Security logs)
- `.csv` exported Security logs

## Steps
1. Trigger Security events on Windows VM:
   - Password failure attempt (4625)
   - User account modification (4738)
   - Successful login (4624)
2. Export Security logs as `.csv`.
3. Transfer `.csv` to Splunk host via USB / shared folder / email.
4. Upload `.csv` to Splunk:
   - Sourcetype: `XmlWinEventLog:Security`
   - Index: `main`
5. Verify ingestion:
   ```spl
   source="windows logs csv.csv" host="DESKTOP-I88F9FT" index="security" sourcetype="csv" failed*



### Splunk enterprise logs
![Event 4724 Screenshot](screenshot1.png)

### Splunk CSV security log upload
![Event 4738 Screenshot](screenshot2.png)

### Windows VM event viewer
![Event 4624 Screenshot](screenshot3.png)

### Powershell failed logons
![CSV Export Screenshot](screenshot4.png)
