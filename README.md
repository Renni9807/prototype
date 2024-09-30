# Grafana and TimescaleDB connection

- Need to change inbound rules in EC2 security group to enable Grafana access to EC2 and allow data retrieval.
  - Open port 3000 for Grafana web interface
  - Open port 5432 for PostgreSQL/TimescaleDB connection

- Need to configure `pg_hba.conf` file in TimescaleDB. 
  - Add `hostssl` entry because Grafana's default setting requires SSL/TLS connection.
  - Example entry: `hostssl all all 0.0.0.0/0 md5`

- Ensure SSL/TLS is properly set up on the TimescaleDB server.

- In Grafana, use 'PostgreSQL' as the data source type when connecting to TimescaleDB.

- Note: Grafana typically uses port 3000 for its web interface, which uses HTTP/HTTPS. The database connection (to port 5432) is separate from this and should be secured with SSL/TLS.


<img width="1200" alt="OHLCV Trend Graph" src="https://github.com/user-attachments/assets/33b436ca-41bd-4cfe-b4cb-84bcea5bd14a">
<img width="1200" alt="swap" src="https://github.com/user-attachments/assets/9c2efb39-3e73-439d-aef1-1a00017f6708">
<img width="1200" alt="mint" src="https://github.com/user-attachments/assets/36f7f48f-23b2-4d0f-ae8d-472ea46a8897">
<img width="1200" alt="burn" src="https://github.com/user-attachments/assets/204174af-c2ec-4fe5-a17d-f9051d444c0f">
