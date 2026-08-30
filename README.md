# NW-of-World
News
cd /home/workdir/artifacts
pip install -r requirements.txt
streamlit run commodity_dashboard_v2.py
import webview
import subprocess
import sys
import time
import threading

def start_streamlit():
    subprocess.Popen([sys.executable, "-m", "streamlit", "run", "commodity_dashboard_v2.py", "--server.headless=true"])

threading.Thread(target=start_streamlit, daemon=True).start()
time.sleep(2)  # kurz warten bis Streamlit startet

webview.create_window("Commodity Intelligence Dashboard", "http://localhost:8501", width=1400, height=900)
webview.start()
