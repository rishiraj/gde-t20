# 🏏 T20 World Cup Live Predictor (IND vs ENG)

A real-time, interactive web application built for you and your friends to make live predictions during the T20 World Cup! This app fetches live match data, allows a group of friends to submit their predictions, and uses **Google's Gemini AI** to provide live expert analysis, win probabilities, and projected scores.

## ✨ Features

*   🔴 **Live Match Tracking:** Fetches real-time scores, wickets, and overs using CricAPI.
*   🤖 **AI Expert Analysis:** Uses Google Gemini (gemini-3.1-pro-preview) to analyze the live match context and predict win probabilities and projected scores every 5 minutes.
*   👥 **Group Leaderboard:** Friends can submit their predicted winners and scores.
*   📊 **Interactive Data Visualizations:** Beautiful, auto-updating pie and bar charts (powered by Chart.js) showing both the AI's predictions and the "Group Consensus" of your friends.
*   🎨 **Cricket-Themed UI:** A responsive, mobile-friendly dashboard styled with stadium grass, pitch, and leather ball colors, including a bouncing ball animation!
*   🛡️ **Smart Rate Limiting:** AI predictions are cached for 5 minutes to prevent API exhaustion when 50+ friends are viewing the site simultaneously.
*   🧪 **Mock Data Fallback:** Includes a pre-match simulation mode so you can test the app before the actual match starts.

## 🛠️ Tech Stack

*   **Backend:** Python, Flask
*   **Frontend:** HTML5, CSS3 (CSS Grid/Flexbox), Vanilla JavaScript
*   **Data Visualization:** Chart.js
*   **APIs Used:** 
    *   [Google Gemini API](https://aistudio.google.com/) (AI Analysis & Predictions)
    *   [CricAPI](https://cricketdata.org/) (Live Match Data)

---

## 🚀 Installation & Setup

### 1. Prerequisites
Make sure you have **Python 3.8+** installed on your computer.

### 2. Folder Structure
Ensure your project files are organized exactly like this:
```text
cricket-app/
│
├── app.py              # The Flask backend script
├── .env                # Your secret API keys
│
└── templates/          # MUST be named exactly "templates"
    └── index.html      # The frontend UI
```

### 3. Install Dependencies
Open your terminal or command prompt, navigate to your project folder, and run:
```bash
pip install flask requests python-dotenv google-genai
```

### 4. Configure Environment Variables
Create a file named `.env` in the root folder and add your API keys:
```env
GEMINI_API_KEY=your_actual_gemini_api_key_here
CRICAPI_KEY=your_cricketdata.org_api_key_here
```

### 5. Run the Application
Start the Flask server by running:
```bash
python app.py
```
*Note: Use `python3 app.py` on Mac/Linux if required.*

The app will now be running locally at: **http://127.0.0.1:5000**

---

## 🌍 How to Share with 50+ Friends

Since the app is running locally on your computer, your friends cannot see it yet. To safely share it over the internet for tomorrow's match:

1. Download and install [Ngrok](https://ngrok.com/).
2. Keep your Flask app running in your terminal.
3. Open a **new** terminal window and run:
   ```bash
   ngrok http 5000
   ```
4. Ngrok will generate a public, secure URL (e.g., `https://a1b2-34-56.ngrok-free.app`). 
5. Send this link to your WhatsApp group! Your friends can open it on their phones, submit predictions, and watch the charts update live.

---

## 📝 Important Notes

*   **Pre-Match Testing:** If the IND vs ENG match has not started yet, the app will automatically use a "Mock Data" fallback. It will display simulated scores so you can test the charts and AI. Once the match starts and CricAPI registers the toss, it will seamlessly switch to real live data.
*   **Data Persistence:** Currently, friends' predictions are stored in the server's memory (`user_predictions` list in `app.py`). If you restart the terminal running `app.py`, the leaderboard will clear. 

Enjoy the match! 🏆🏏
