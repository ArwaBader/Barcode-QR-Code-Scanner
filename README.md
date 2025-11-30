# Smart Barcode & QR Code Scanner with Nutritional Analysis

## 📌 Project Overview
This Computer Vision project implements a real-time barcode and QR code scanner using Python in a Google Colab environment. It leverages **OpenCV** for image processing and **Pyzbar** for decoding symbologies. 

Beyond simple scanning, the system integrates with the **Open Food Facts API**. When a commercial food product (EAN-13/UPC) is scanned, the system automatically fetches and displays detailed product metadata, including **brand, ingredients, and nutritional information** (Energy, Fats, Proteins, etc.), effectively acting as a smart dietary assistant.

## 🚀 Key Features
* **Hybrid Decoding**: Capable of detecting and decoding both **QR Codes** (for URLs/Data) and **Barcodes** (EAN-13, UPC) in the same video stream.
* **Cloud-Based Acquisition**: Implements a JavaScript-to-Python bridge to access the user's webcam directly within a Google Colab notebook.
* **Live Database Integration**: Connects to the **Open Food Facts** global database to retrieve real-time product data.
* **Image Preprocessing**: Uses Grayscale conversion for robust detection in varying lighting conditions.

## 🛠️ Technologies & Libraries Used
* **Python 3.x**
* **OpenCV (`cv2`)**: Image manipulation and processing.
* **Pyzbar**: Barcode and QR code decoding.
* **Requests**: HTTP library for API communication.
* **Matplotlib**: Visualization of the captured scan.
* **NumPy**: Array handling for image data.
* **Google Colab**: Runtime environment.

## 📂 Data Source
Unlike traditional CV projects that require downloading static datasets for training, this project utilizes a **Live Data Retrieval Model**:
* **Source**: [Open Food Facts API](https://world.openfoodfacts.org/data)
* **Access Method**: REST API (HTTP GET requests)
* **Data Points**: Product Name, Brands, Nutriments (Energy, Fat, Carbs, Proteins), Ingredients, and Image URLs.

*No local dataset download is required to run this project.*

## 👥 Team Members & Contributions
The project workload was divided among the team members as follows:

| Name | ID | Primary Responsibility |
| :--- | :--- | :--- |
| **Arwa Alqassab** | 202101531 | **Implementation, Database & Repository** |
| **Ghala Alshahrani** | 202101402 | **Abstract & Introduction** |
| **Renad Alnitaifi** | 202200262 | **Theory & Method** |
| **Shahad Alshowaikhat** | 202101791 | **Results & Analysis** |
| **Batoul Nourallah** | 202300946 | **Conclusion & Future Work** |

### 🛠️ Detailed Contribution Breakdown
* **Arwa Alqassab**: Lead Developer. Responsible for the Python implementation, identifying and integrating the Open Food Facts API (Dataset), and managing the GitHub repository.
* **Ghala Alshahrani**: Conducted initial research and code searching. Authored the Abstract and Introduction sections of the report.
* **Renad Alnitaifi**: Documented the theoretical background and methodology used in the computer vision pipeline.
* **Shahad Alshowaikhat**: Analyzed the system's performance and compiled the Results & Analysis section.
* **Batoul Nourallah**: Summarized the project findings in the Conclusion and outlined potential Future Work.

## ⚙️ Setup & Installation
Since this project is designed for **Google Colab**, the setup is minimal.

1.  **Clone the Repository**
    ```bash
    https://colab.research.google.com/drive/17iZ7F9hIZ5Da-e7X_pa-qD8cAZhgvN1w?usp=sharing
    ```
2.  **Open in Google Colab**
    * Upload the `Project_CV.ipynb` file to your Google Drive.
    * Open the file with Google Colab.

3.  **Install System Dependencies**
    The first code cell in the notebook handles the installation of the required system libraries (`libzbar0`) which are not present by default in Colab.
    ```python
    !pip install pyzbar
    !apt-get install -y libzbar0
    ```

## 💻 How to Run
1.  **Execute the Installation Cell**: Run the first cell to install `pyzbar`.
2.  **Run the Main Code Block**: Execute the cell containing the `take_photo()`, `get_product_info()`, and main logic.
3.  **Grant Permissions**: The browser will ask for permission to access your webcam. Click **Allow**.
4.  **Scan an Item**:
    * Hold a **QR Code** or a **Food Product Barcode** (e.g., a soda can, chocolate bar) in front of the camera.
    * Click the **"Capture"** button that appears in the output area.
5.  **View Results**:
    * **QR Code**: The decoded link/text will be printed below the image.
    * **Product Barcode**: The system will print the Product Name, Brand, and Nutritional Facts table.

## 📜 License
This project is open-source and available under the MIT License.
