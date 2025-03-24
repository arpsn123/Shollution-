# 🧠 NeuroSholl: Quantifying Neuronal Complexity with Sholl Analysis  
<div align="center">
    <img src="https://img.shields.io/github/stars/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=ffca28" alt="GitHub Repo Stars">
    <img src="https://img.shields.io/github/forks/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=00aaff" alt="GitHub Forks">
    <img src="https://img.shields.io/github/watchers/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=00e676" alt="GitHub Watchers">
</div>

<div align="center">
    <img src="https://img.shields.io/github/issues/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=ea4335" alt="GitHub Issues">
    <img src="https://img.shields.io/github/issues-pr/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=ff9100" alt="GitHub Pull Requests">
</div>

<div align="center">
    <img src="https://img.shields.io/github/last-commit/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=673ab7" alt="GitHub Last Commit">
    <img src="https://img.shields.io/github/contributors/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=388e3c" alt="GitHub Contributors">
    <img src="https://img.shields.io/github/repo-size/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=303f9f" alt="GitHub Repo Size">
</div>

<div align="center">
    <img src="https://img.shields.io/github/languages/count/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=607d8b" alt="GitHub Language Count">
    <img src="https://img.shields.io/github/languages/top/arpsn123/Shollution-?style=for-the-badge&logo=github&logoColor=white&color=4caf50" alt="GitHub Top Language">
</div>

<div align="center">
    <img src="https://img.shields.io/badge/Maintenance-%20Active-brightgreen?style=for-the-badge&logo=github&logoColor=white" alt="Maintenance Status">
</div>


## 📌 Overview  

Neurons form the foundation of brain function, and their **branching complexity** is a critical aspect of how they process information. Understanding neuronal morphology can provide insights into **developmental neuroscience, neurodegenerative diseases, and computational neuroscience models**.  

One of the most widely used methods to quantify neuronal branching is **Sholl Analysis**, a mathematical technique that examines how a neuron's dendritic complexity changes with distance from the soma (cell body). By analyzing where branches intersect with a series of concentric circles centered on the soma, researchers can evaluate how neurons grow, remodel, or deteriorate under various conditions.  

This repository provides a **fully automated computational approach** to Sholl Analysis, leveraging:  
- **Automated vs. manual soma detection** for precise image processing  
- **Polynomial regression** for capturing non-linear growth patterns  
- **Advanced model evaluation** using statistical metrics like **R², AIC, and BIC**  

---

## 📖 Understanding Sholl Analysis  

### 🔬 Why Analyze Neuronal Branching?  
Neurons form intricate networks, where dendrites receive signals and pass them to the soma for processing. The **degree of branching** influences:  
- **Information integration:** More branches allow more synaptic connections.  
- **Neuroplasticity:** Dendritic remodeling occurs in response to learning and memory.  
- **Disease progression:** Neurodegenerative conditions like Alzheimer's are marked by dendritic atrophy.  

Sholl Analysis quantifies **how dendritic complexity changes with distance from the soma**, revealing critical insights into neuronal structure and function.  

### 🔹 How Sholl Analysis Works  
1. **Placing Concentric Circles:** Starting from the soma, evenly spaced circles are drawn outward.  
2. **Counting Intersections:** The number of dendritic branches crossing each circle is recorded.  
3. **Plotting the Profile:** A curve is generated, showing how branching density changes with distance.  
4. **Fitting a Mathematical Model:** To capture trends in branching patterns, we apply polynomial regression.  

---

## 🏹 Soma Detection: Automated vs. Manual  

A fundamental step in Sholl Analysis is **identifying the soma**, as it serves as the reference point for all measurements. This project supports two methods:  

### 🔹 **Automated Soma Detection** (Less Accurate)  
- Uses **OpenCV’s minMaxLoc() function** to find the **brightest pixel**, assuming it corresponds to the soma.  
- A **binary mask** is generated to determine the centroid.  
- **Problem:** This method is highly **sensitive to uneven lighting**, which can misidentify the soma in complex images.  

### 🔹 **Manual Soma Selection** (More Accurate)  
- The user **clicks on the soma**, ensuring precise placement.  
- Eliminates errors caused by variations in image intensity.  
- **Trade-off:** Requires manual input, making it slightly slower but significantly more reliable.  

**Conclusion:** Automated detection is not always reliable, especially in high-noise images. **Manual selection is recommended** for greater accuracy.  

---

## 📊 Polynomial Regression for Improved Analysis  

Instead of assuming a simple linear relationship between distance and branching complexity, this approach uses **polynomial regression** to fit a more flexible curve to the data.  

### **Why Polynomial Regression?**  
- **Neuronal branching does not follow a simple pattern**—a higher-degree polynomial can better model changes in complexity.  
- **Polynomial models capture the peak branching density** and its decline with distance.  
- **It smooths the data**, reducing the effects of noise in raw intersection counts.  

By fitting a polynomial of degree **4**, this model ensures that small variations in the data do not distort the overall trend.  

---

## 📈 Key Metrics for Model Evaluation  

### ✅ **R-Squared (R²)**  
Measures how well the polynomial regression fits the data. A higher R² value indicates that the model accurately represents dendritic complexity.  

### ✅ **Akaike Information Criterion (AIC)**  
A metric used to balance **model accuracy vs. complexity**. A lower AIC means the model fits well **without overfitting**.  

### ✅ **Bayesian Information Criterion (BIC)**  
Similar to AIC but imposes a **harsher penalty on complex models**. Helps ensure that the polynomial degree is not unnecessarily high.  

---

## Tech Stack

### Programming Language
- ![Python](https://img.shields.io/badge/Python-3.9-blue.svg?style=for-the-badge&logo=python)

### Frameworks and Libraries
- ![NumPy](https://img.shields.io/badge/NumPy-1.24.2-blue.svg?style=for-the-badge&logo=numpy)
- ![SciPy](https://img.shields.io/badge/SciPy-1.10.1-blue.svg?style=for-the-badge&logo=scipy)
- ![OpenCV](https://img.shields.io/badge/OpenCV-4.6.0-5C3A3A.svg?style=for-the-badge&logo=openCV)
- ![matplotlib](https://img.shields.io/badge/matplotlib-3.6.0-blue.svg?style=for-the-badge&logo=matplotlib)
- ![Pandas](https://img.shields.io/badge/Pandas-1.5.3-blue.svg?style=for-the-badge&logo=pandas)
- ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.2.2-blue.svg?style=for-the-badge&logo=scikitlearn)

### Tools and Platforms
- ![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange.svg?style=for-the-badge&logo=jupyter)
- ![Google Colab](https://img.shields.io/badge/Google_Colab-free-lightgreen.svg?style=for-the-badge&logo=googlecolab)

### Development and Version Control
- ![Git](https://img.shields.io/badge/Git-2.47.0-orange.svg?style=for-the-badge&logo=git)
- ![GitHub](https://img.shields.io/badge/GitHub-arpsn123-success.svg?style=for-the-badge&logo=github)


## 📌 Results & Key Takeaways  

✔ **Sholl Analysis helps quantify dendritic complexity**, revealing key insights into neuronal structure.  
✔ **Polynomial regression** provides a better fit than simple linear models, capturing non-linear growth trends.  
✔ **Manual soma detection is significantly more accurate** than automated methods in unevenly illuminated images.  
✔ **Future Work:** Exploring deep learning-based soma detection for improved automation.  

This repository is a powerful tool for neuroscientists, bioinformaticians, and computational researchers looking to analyze neuronal branching patterns with greater precision. 🚀
