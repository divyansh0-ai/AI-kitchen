# 🍳 AI Kitchen - Smart Recipe Generator

AI Kitchen is an intelligent recipe generation web application that provides personalized recipes, nutritional information, and cooking unit conversion tools powered by AI.

![AI Kitchen](https://img.shields.io/badge/Status-Active-success)
![Python](https://img.shields.io/badge/Python-3.8+-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104-green)

## ✨ Features

- 🤖 **AI-Powered Recipe Generation** - Get personalized recipes based on dish names
- 🥗 **Ingredient-Based Search** - Find recipes from available ingredients with smart filtering (Tasty, Healthy, Quick)
- 📊 **Detailed Nutrition Info** - Comprehensive nutritional breakdown for every recipe
- 🔄 **Unit Normalizer** - Convert cooking measurements between different units
- ❤️ **Favorite Recipes** - Save and manage your favorite recipes locally
- 🔀 **Ingredient Alternatives** - Get smart ingredient substitution suggestions
- 📏 **Servings Adjustment** - Dynamically scale ingredient quantities
- 🎨 **Modern UI** - Beautiful, responsive interface with smooth animations
- 🌱 **Dietary Badges** - Automatic detection of Vegan, Vegetarian, and Non-Veg dishes

## 🛠️ Technologies Used

### Backend
- **FastAPI** - Modern Python web framework
- **Google Gemini AI** - Recipe generation and intelligence
- **TheMealDB API** - Recipe database
- **Pexels API** - High-quality food images
- **HTTPX** - Async HTTP client

### Frontend
- **HTML5** - Semantic markup
- **CSS3** - Modern styling with gradients and animations
- **JavaScript (ES6+)** - Interactive functionality
- **Local Storage** - Client-side data persistence

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Python 3.8 or higher** - [Download Python](https://www.python.org/downloads/)
- **pip** - Python package manager (comes with Python)
- **Git** (optional) - For cloning the repository

## 🚀 Installation & Setup

### 1. Clone or Download the Project

bash
# If using Git
git clone <your-repository-url>
cd recipe_unit_normalizer

# Or download and extract the ZIP file


### 2. Create a Virtual Environment (Recommended)

bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate


### 3. Install Dependencies

bash
pip install -r requirements.txt


The `requirements.txt` includes:
- fastapi==0.104.1
- uvicorn==0.24.0
- httpx==0.25.1
- python-dotenv==1.0.0
- google-generativeai==0.3.1
- requests==2.31.0
- pydantic==2.5.0

### 4. Configure Environment Variables

Create a `.env` file in the project root directory:

bash
# Windows
copy .env.example .env

# macOS/Linux
cp .env.example .env


Edit the `.env` file and add your API keys:

env
GEMINI_API_KEY=your_google_gemini_api_key_here
PEXELS_API_KEY=your_pexels_api_key_here


#### How to Get API Keys:

**Google Gemini API Key:**
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Create a new API key
4. Copy and paste it into the `.env` file

**Pexels API Key:**
1. Visit [Pexels API](https://www.pexels.com/api/)
2. Sign up for a free account
3. Generate an API key
4. Copy and paste it into the `.env` file

### 5. Run the Application

bash
python app.py


The server will start on `http://localhost:8001`

You should see output similar to:

INFO:     Started server process
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Uvicorn running on http://127.0.0.1:8001


### 6. Access the Application

Open your web browser and navigate to:

http://localhost:8001


## 📖 Usage Guide

### Generate a Recipe

1. **By Dish Name:**
   - Click on **"New Recipe"** mode
   - Enter a dish name (e.g., "Chicken Biryani", "Vegan Buddha Bowl")
   - Click the search button
   - View detailed recipe with ingredients, instructions, and nutrition

2. **By Ingredients:**
   - Click on **"Parse Text"** mode
   - Enter available ingredients separated by commas
   - Choose filter: **Tasty**, **Healthy**, or **Quick**
   - Click search to get matching recipes

### Unit Conversion

1. Navigate to **"Unit Normalizer"** in the top menu
2. Enter the value to convert
3. Select the source unit (From)
4. Select the target unit (To)
5. Click **"CONVERT"** - the result appears instantly

### Save Favorites

- Click the **heart icon** on any recipe to save it
- Access saved recipes from **"My Recipes"** in the top menu
- Click on any saved recipe to view it again

### Adjust Servings

- On any recipe, use the **+/-** buttons next to servings
- Ingredient quantities automatically scale

### Find Ingredient Alternatives

- Click **"Replace"** next to any ingredient
- View AI-suggested alternatives and substitution notes

## 📁 Project Structure

recipe_unit_normalizer/
│
├── app.py                 # FastAPI backend server
├── index.html             # Main HTML file
├── style.css              # Styling and animations
├── script.js              # Frontend JavaScript logic
├── requirements.txt       # Python dependencies
├── .env                   # Environment variables (create this)
├── .env.example          # Example environment file
└── README.md             # This file


## 🔧 Configuration

### Port Configuration

To change the server port, edit `app.py`:

python
if __name__ == "__main__":
    uvicorn.run(app, host="127.0.0.1", port=8001)  # Change port here

### CORS Settings

CORS is configured to allow all origins. To restrict, edit in `app.py`:

python
app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost:8001"],  # Specify allowed origins
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)

## 🐛 Troubleshooting

### Server won't start

**Error:** `Address already in use`
- **Solution:** Change the port in `app.py` or kill the process using port 8001

**Error:** `No module named 'fastapi'`
- **Solution:** Ensure you've activated the virtual environment and run `pip install -r requirements.txt`

### API Errors

**Error:** `Invalid API key`
- **Solution:** Check that your `.env` file has valid API keys with no extra spaces

**Error:** `Rate limit exceeded`
- **Solution:** Wait a few minutes or upgrade your API plan

### UI Not Loading

- Check browser console (F12) for JavaScript errors
- Ensure `style.css` and `script.js` are in the same directory as `index.html`
- Clear browser cache (Ctrl+Shift+R)

### Recipes Not Displaying

- Check server logs for API errors
- Verify internet connection
- Ensure backend is running on `http://localhost:8001`

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- **Google Gemini AI** - Recipe generation
- **TheMealDB** - Recipe database
- **Pexels** - Food photography
- **FastAPI** - Web framework
- **Unsplash** - Additional food images

## 📧 Support

For issues or questions, please open an issue on the repository or contact the maintainer.

**Made with ❤️ and AI**
# AI-kitchen
it is for helping people across all our world to normalize the unites and also sharing recipe.
