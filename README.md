# Streamlit Uploads Library

[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://hreikin-streamlit-uploads-library-home-ar6h9h.streamlit.app/)

A simple gallery for use in Streamlit projects. Check out the demo using the Streamlit Cloud button above.

## Installation

Installation is available via pip:

```
pip install streamlit-uploads-library
```

## Usage

Using the gallery is simple, import `streamlit_uploads_library` and then instantiate the class with the 
required `directory` variable. Other options can be configured by passing in different variables 
when instantiating the class.

- `directory` (required): A `str()` of the path to the folder containing the gallery images, for example, `"assets"`.
- `expanded` (optional): A `bool()`, passing `False` starts the expander type gallery closed, default is open and `True`.
- `file_extensions` (optional): A `tuple()` containing strings of the file extensions to include in the gallery, default is `(".png", ".jpg", ".jpeg")`.
- `gallery_type` (optional): A `str()` with either "container" or "expander" used as the keyword, the default is `"container"`.
- `label` (optional): A `str()` containing the name of the gallery, passing `None` disables the label. The default value is `"Gallery"`.
- `number_of_columns` (optional): An `int()` defining the number of required columns, default is `5`.
- `show_filenames` (optional): A `bool()`, passing `True` displays the filenames, the default is `False` which hides them.

```python
import streamlit as st
from streamlit_uploads_library import ImageGallery

st.set_page_config(page_title="Streamlit Uploads Library", layout="wide")
default_gallery = ImageGallery(directory="assets")
gallery_with_columns = ImageGallery(directory="assets", label="**Gallery - Columns**", number_of_columns=3)
expander_gallery = ImageGallery(directory="assets", expanded=True, gallery_type="expander", label="**Gallery - Expander**")
multiple_options_gallery = ImageGallery(directory="assets", gallery_type="expander", label="**Gallery - Multiple Options**", number_of_columns=3, show_filename=False)
```

To run the example application provided in the repository:

```bash
git clone https://github.com/hreikin/streamlit-uploads-library
cd streamlit-uploads-library/
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
streamlit run Home.py
```