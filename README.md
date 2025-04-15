# 🖼️ ImageScraper

**ImageScraper** is a modular and scalable tool to automate the scraping and downloading of high-quality images from popular platforms such as Pinterest, Unsplash, and Lummi. Built using Playwright for browser automation and BeautifulSoup for parsing, it enables easy customization of sources and efficient concurrent downloading of images based on search keywords.

---

## 🚀 Features

- 🔍 Search and download images by keyword.
- 🌐 Scrape multiple sources: Pinterest, Unsplash, and Lummi.
- 🧩 Modular architecture — easily extendable to new sources.
- ⚙️ Configurable via environment variables.
- 🧵 Multi-threaded downloads using `ThreadPoolExecutor`.
- 🐳 Docker support for consistent deployment.

---

## 📷 Available Image Sources

The following sources are currently supported:

- **Pinterest** – Search and download pins based on your keyword.
- **Unsplash** – Free high-resolution photos from photographers.
- **Lummi** – AI-generated visual content from Lummi.ai.

> ℹ️ You can enable/disable each scraper individually through environment variables in your `.env` file.

---

## 📦 Installation

1. **Clone the repository**

```bash
git clone https://github.com/your-username/ImageScraper.git
cd ImageScraper
```

2. **Install dependencies**

Create a virtual environment and install packages:

```bash
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
```

Alternatively, use Docker (see below).

---

## ⚙️ Configuration

Copy and edit the example environment file:

```bash
cp .env.example .env
```

Available environment variables:

- `SEARCH`: The search keyword (e.g., `architecture`)
- `LUMMMI_SCRAPER`: Enable Lummi scraper (`true` or `false`)
- `PINTEREST_SCRAPER`: Enable Pinterest scraper (`true` or `false`)
- `UNSPLASH_SCRAPER`: Enable Unsplash scraper (`true` or `false`)
- `SCROLL_TIMEOUT`: Scrolling duration on each site (in seconds)

---

## 🐳 Running with Docker

To build and run the scraper inside Docker:

```bash
docker compose up --build
```

Images will be saved in the `downloads/` directory.  
⚠️ Make sure to set the environment variables in your `.env` file before running the container.  
📁 You can edit `.env` or set them inline when running with Docker if preferred.

---

## 🧠 Usage (Python)

Run the scraper directly with:

```bash
python src/main.py
```

Make sure your `.env` is configured properly before launching.

---

## 📁 Output Structure

Downloaded images are saved in:

```
downloads/
└── <search_term>/
    ├── Pinterest/
    ├── Unsplash/
    └── Lummi/
```

---

## 🛠️ Tech Stack

- Python 3.12+
- [Playwright](https://playwright.dev/python/)
- [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/)
- [Requests](https://docs.python-requests.org/)
- Docker & Docker Compose

---

## 📌 Notes

- Ensure your system meets the Playwright requirements: run `playwright install` if running manually.
- `ImpossibleImagesScraper` is present but currently disabled and commented out in the code.


---

## 📃 License

MIT License – see `LICENSE` file for details.

