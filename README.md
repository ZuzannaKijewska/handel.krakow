# handel.krakow
import pandas as pd
import sqlite3
excel_file = "Kraków.xlsx"
sheet_name = "Kraków"
df = pd.read_excel(excel_file, sheet_name=sheet_name)
db_name = "sprzedaz_krakow.db"
conn = sqlite3.connect(db_name)
df.to_sql("sprzedaz", conn, if_exists="replace", index=False)
conn.close()
