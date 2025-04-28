
# Xtension - Control Your X Feed with LLM Filtering

Xtension is a browser extension designed to enhance your X (formerly Twitter) experience by filtering out unwanted content such as engagement bait and inflammatory posts. By leveraging the power of Large Language Models (LLMs) from Groq's ultra-fast API, Xtension gives you greater control over what you see in your feed.

See How the Extension works here : https://drive.google.com/file/d/1rmFFxOHQR9XCX4I9Dm7Z-rC-NpTZfN00/view?usp=sharing

## How It Works

Xtension actively monitors your X feed as you scroll and dynamically filters tweets based on your preferences:

1.  **Real-time Detection:** The extension's content script, injected into the X webpage, detects new tweets as they appear in your viewport. It identifies tweets that are at least 30% visible on your screen.
2.  **Content Analysis via Groq:** When a new tweet is detected, its text content (currently text-only) is extracted and sent to Groq's API for analysis using a language model of your choice. This API call is handled efficiently within the extension's service worker.
3.  **Intelligent Filtering:** Based on the analysis from Groq, tweets identified as engagement bait, political content (or any other category defined by the user), are flagged for filtering.
4.  **Dynamic Blurring and Hiding:** The content script then modifies the style of these flagged tweets, blurring and effectively hiding them from your immediate view.
5.  **User Control:** You retain complete control. With a single click on a blurred tweet, you can instantly reveal its content.
6.  **Customizable Filtering:** The extension's settings page allows you to input your Groq API key and, more importantly, customize the system prompt used for content analysis. This enables you to fine-tune the filtering behavior according to your specific needs and preferences.

## Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository_url>
    cd xtension
    npm run build
    ```

2.  **Install the extension in Chrome (or Chromium-based browser):**
    * Open Chrome and navigate to `chrome://extensions/`.
    * Enable "Developer mode" in the top right corner.
    * Click "Load unpacked" in the top left corner.
    * Select the directory where you cloned, and upload dist folder.
      
3.  **Obtain your Groq API key:**
    * Sign up for an account on [Groq's website](https://console.groq.com/).
    * Retrieve your API key from your Groq dashboard.

4.  **Configure Xtension:**
    * Click on the Xtension icon in your browser's toolbar.
    * Navigate to the extension's settings page.
    * Enter your Groq API key in the designated field.
    * Optionally, customize the system prompt to adjust how tweets are analyzed and filtered. Experiment with different prompts to achieve your desired filtering behavior.

## Tech Stack

* **Frontend:** REACT
* **LLM Integration:** Groq API
* **Language Model:** User-selectable LLM available through Groq's API
* **Browser Compatibility:** Chrome and other Chromium-based browsers

## Contributing

Contributions to Xtension are welcome! If you have ideas for improvements, new features, or bug fixes, please feel free to:

1.  Fork the repository.
2.  Create a new branch for your changes.
3.  Implement your changes and write clear commit messages.
4.  Submit a pull request.
