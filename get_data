import gspread
from oauth2client.service_account import ServiceAccountCredentials
import pandas as pd

#credentials
creds={
  "type": "service_account",
  "project_id": "kri-auto-dashboard",
  "private_key_id": "40fc01f02a01a0af207dfe3da4780f151dce2ac2",
  "private_key": "-----BEGIN PRIVATE KEY-----\nMIIEvgIBADANBgkqhkiG9w0BAQEFAASCBKgwggSkAgEAAoIBAQCve3FWodZ9ckmV\nhOgNHKpIlGFUtgT5nLkDMKGHq3iTtYkvzEdHQ432l1W/EGjd7bmNJRvoMN4v5LU5\n6hi3ebwToA3Dr2KbvADvADeV7nIRkGHV5LEmNWXbZloKfOzrDIgU9+d/hN8wkE0C\nl/ddKJXwKE7i74iDdBzMwEeCrR2HDk0fRBGX7BTgwzi8tpyfO6kzmY/mwS10ZWqT\nHLgC5RqQUgx6N+Z1uYjDGQcPCbtBtN/37VCTHTVW1lgFerxPtTflBg9YpUycmyGT\nWY7Lm2ROUGc/VMeh6RBLnv11ToBZcaOz7hImcC1ot3RI5y8PRdDbF+OVRBIhDE0D\n01JuBEbTAgMBAAECggEASyVJASi3oaut0B4Egwzp7L/BuFVj5wJShgeuvFrU/Sfp\nkfLf+Sf4JIdk3DdqONMiuMsR2soGc6r0YlMZd4RlYmARVOGHkBofqjlFFGryJQxX\noRFYPPzz29LGLySVDgilQ5lvZH+hVfoNSFWMQ7PsFVYlhe++XVB9Pr7+QHrioKDs\ndKh+tvL26rRK5Fzw3k9dALVDbmHbLdvjl/kz+GWoJW1E+bgRDtFi/2Ctn08PW+K/\n4WmnifNYN/bIkYAAQh6kU8nj9hMIa1Z+YvB3v1edUlzSM5U/IVUunaQ82yPf95ZY\nW1KaMlhYxQQXowv5tfC21uqoeLvWO4Pp5kF6PtK6HQKBgQDnRNEwo6gOjF2Cy7eD\nm7EidyL6t87l8xpqVeMp1dqCmcVcnVi7so886anVTNV1moScqqlF51C0svWvHU5A\nUGg7bcJ3+H6TnISNiGBDXioSG5s/uXHyDxdi59rtWj2fsYTh3KDr7z8daageXJPI\nJsWK52PZAzpkkCSEUHzPKyndpwKBgQDCP2s8XDBzUgvo6tq8Zb/U3mKKcOrisD8+\nSYXehlj+1qa3j80HwPek9U8hju7mIAP2/KterFaNCwSsK4K19yo6VwjZUoFJ+G5j\nPwUS5F2LHlwsvdcGK16zlJsGFPmY/r5jBcE1/NyTLcdYOs33HcAh+pFHagWjJ6D9\neTJJCvRq9QKBgQCK3rbihxMuETlBhgRfQcke0f0uIdtaFx1ghsxOXbzFOYLadx1G\nMBV01TaG/4kaAjvpO01DzX+X0fJXQbiwQ9gi/2iL06pmBtFNj3uGWG/Yybzyie+T\nE17OpDzA07Q3RUhuu6Xhppr2lXA/MwYGZMmv+/vn3tlcc3WKAi6/08Ji9wKBgQCN\nuUe8WmbfPNWDsxa0rmgwH7E14Pz/OChsgagym0MDbAlnlHu7VIday8BYc7jKHkHG\nSsOd54+eiJN4KqbLrPIabrX+GbxLA/9GWgyRpBy8DAKkgj4IOkx2Kc6RuWwCvJqc\nFO7LPRqSJ6xyKzVrP0GXiQHGYQyL5bYIOgz+TgfWoQKBgBLnz0CKbMyfSVoAZqrz\nIVxGPL8oEa05BV87BeSWbSul+1ajFwksYN5VrD/lNGe7PzGJ/VB1z6Af4OjO81ZD\nhl+viw6vSAw75sEIUt+G1+6JCB/9dwu4ajhj6AZC5nHDop25bCVPBSpQ3py742GI\nKbvg+Z3+JOGzg87pbhyZ1s8i\n-----END PRIVATE KEY-----\n",
  "client_email": "kri-auto@kri-auto-dashboard.iam.gserviceaccount.com",
  "client_id": "109436484526841420688",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "https://www.googleapis.com/robot/v1/metadata/x509/kri-auto%40kri-auto-dashboard.iam.gserviceaccount.com",
  "universe_domain": "googleapis.com"
}
# Define the URL of your Google Sheets document
gsheet_url = "https://docs.google.com/spreadsheets/d/1Ftxob0a-paGitcTzslZ8CQlYk6EaNdDFNWLa2A82FsE/edit#gid=0"

# Set up the Google Sheets API credentials
scope = ["https://spreadsheets.google.com/feeds", "https://www.googleapis.com/auth/drive"]
creds = ServiceAccountCredentials.from_json_keyfile_name(r'C:\Users\5060916\Desktop\creds.json', scope)
client = gspread.authorize(creds)

# Open the Google Sheets document by its URL
doc = client.open_by_url(gsheet_url)

# Select the specific worksheet by title or index (e.g., by title)
worksheet = doc.worksheet("Suivi")

# Read the data from the worksheet
data = worksheet.get_all_values()

# Create a Pandas DataFrame
df = pd.DataFrame(data[1:], columns=data[0])

# Display the DataFrame
df.head(30)
