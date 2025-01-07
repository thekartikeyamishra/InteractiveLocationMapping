# **Interactive Location Mapping Tool**

## **Overview**

The **Interactive Location Mapping Tool** is a Python-based application that allows users to generate an interactive map for a specified location. Using the **`folium`** library for map visualization and **`geopy`** for geocoding, the tool fetches the latitude and longitude of a location and displays it on an interactive map.

This tool is particularly useful for:
- Visualizing specific locations on a map.
- Geocoding locations to fetch latitude and longitude.
- Educational purposes for understanding geocoding and map visualizations.

---

## **Features**

1. **Interactive Map**:
   - Generates a map using the `folium` library centered on the specified location.
   - Zoom functionality allows you to explore the surrounding area.

2. **Location Geocoding**:
   - Converts a location name (e.g., city, landmark) into latitude and longitude using `geopy`.

3. **Custom Markers**:
   - Places a marker on the map to highlight the location.

4. **User-Friendly Input**:
   - Accepts a location name as input and instantly processes it.

---


## **Installation Instructions**

### Step 1: Clone the Repository
First, clone the repository to your local machine:
```bash
git clone [https://github.com/thekartikeyamishra/InteractiveLocationMapping.git](https://github.com/thekartikeyamishra/InteractiveLocationMapping).git
cd InteractiveLocationMapping
```

### Step 2: Set Up a Virtual Environment (Optional)
It’s recommended to create a virtual environment to manage dependencies:
```bash
python -m venv .venv
source .venv/bin/activate       # On Windows: .venv\Scripts\activate
```

### Step 3: Install Dependencies
Install the required Python libraries:
```bash
pip install -r requirements.txt
```

The `requirements.txt` file includes:
```
folium
geopy
IPython
```

---

## **How to Use**

### Step 1: Run the Script
Execute the `map_tool.py` script:
```bash
python map_tool.py
```

### Step 2: Enter a Location
- The program will prompt you to enter a location. For example:
  ```
  Enter your location: Eiffel Tower, Paris
  ```

### Step 3: View the Map
- If the location is valid, an interactive map will be displayed in your browser.
- A marker will indicate the exact location.

### Step 4: Handle Errors
- If the location cannot be found, the program will display an error message:
  ```
  Location not found. Try again!!
  ```

---

## **Code Walkthrough**

### 1. **Geocoding with `geopy`**:
The **`Nominatim`** geocoder fetches the latitude and longitude for the entered location:
```python
geolocator = Nominatim(user_agent="geoapi")
location = geolocator.geocode(location_name)
```

### 2. **Map Visualization with `folium`**:
The `folium.Map` object creates an interactive map centered at the fetched coordinates:
```python
map_object = folium.Map(location=[latitude, longitude], zoom_start=12)
```

### 3. **Adding Markers**:
A marker is added to highlight the location on the map:
```python
marker = folium.Marker([latitude, longitude], popup=location_name)
marker.add_to(map_object)
```

### 4. **Displaying the Map**:
The map is displayed interactively in the Jupyter Notebook or browser:
```python
display(HTML(map_object._repr_html_()))
```

---

## **Example**

### Input:
```
Enter your location: Times Square, New York
```

### Output:
- A map centered on **Times Square** with a marker indicating its exact location.

---

## **Error Handling**

1. If the location is invalid or not found:
   ```
   Location not found. Try again!!
   ```

2. If the `folium` library or other dependencies are not installed, follow the installation instructions above.

---

## **Potential Enhancements**

1. **Multiple Locations**:
   - Extend the tool to accept multiple locations and plot them simultaneously.

2. **Save Map as HTML**:
   - Add functionality to save the generated map as an HTML file for offline use.

3. **Location Search**:
   - Integrate a search bar for real-time map updates.

4. **Route Mapping**:
   - Enhance the tool to display routes between two or more locations.

---

## **Use Cases**

1. **Travel Planning**:
   - Visualize landmarks, cities, or any custom locations for trip planning.

2. **Education**:
   - Teach concepts of geocoding and interactive maps.

3. **Custom Mapping Applications**:
   - Build tools to visualize geographical data for various applications.

---

## **Contribute**

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-name
   ```
3. Make changes and commit:
   ```bash
   git commit -m "Add new feature"
   ```
4. Push the branch and open a pull request:
   ```bash
   git push origin feature-name
   ```

---

## **Support**

If you find this project useful, give it a ⭐ on GitHub: [Interactive Location Mapping Tool](https://github.com/thekartikeyamishra/InteractiveLocationMapping).

---
