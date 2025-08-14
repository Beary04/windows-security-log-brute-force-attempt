# Splunk Security Event Lab

## Objective
Demonstrate ingestion and analysis of Windows Security logs in Splunk, highlighting key events like password failed logons (4725), account changes (4738), and successful logons (4624).

## Tools Used
- Splunk Enterprise (host)
- Windows 10 VM (source of Security logs)
- `.csv` exported Security logs

## Steps
1. Trigger Security events on Windows VM:
   - Password failure attempt (4725)
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



!image[image alt](https://github.com/Beary04/windows-security-log-brute-force-attempt/blob/main/Screenshot%20(10).png?raw=true)
