# Using PCA to analyze the food texture data
In this project, we conduct the experiment of PCA on Food texture data to represent data into low-dimensional space. Then explore the meaning of each component in term of describing entire data.

## Environment
Project is created with:
* Numpy version: 1.20.3
* Pandas version: 1.3.0
	
## Setup
Install the requirements before runing the **Food texture analysis.ipynb**

```
pip install numpy==1.20.3
pip install pandas==1.3.0
```
## Pseudo-code of PCA

1.   Collecting Data.

2.  Exploring and Preprocessing Data. (Data Wrangling)

    - Stored Data (using Pandas Dataframe)

    -  Visualizing data distribution (Pandas Built-in function)

    -  Mean Centering.

        ``` {xleftmargin="-1cm"}
        Mean_X  = X -- X.mean()
        ```

    - Standardizing.

        ``` {xleftmargin="-1cm"}
        Standard_X  = Mean_X /  X.std() 
        ```

3.  Computing Covariance Matrix.

        A = Standard_X.T @ Standard_X / Standard_X.shape[1]

4.  Computing Eigenvalues and Eigenvectors from Covariance matrix.
    (Using numpy built-in function: *np.linalg.eig*)

5.  Choose the best k components satisfying threshold.

        Contributed_percent = eigenvalues / sum(eigenvalues)

        For k in range(len(Contributed_percent)):
            If sum(Contributed_percent[:k]) > threshold:
                return k

6.  Transforming data into new space.

        P = A @ Eigenvectors_selected

## Conclusion
Starting with 5 measurements. After applying PCA algorithm, the represent space are reduced to 2 components with the following implicit meaning:
- The first component indicates that the strong correlation with the Oil, Crispy, while the opposite was true for the Density and Fracture.

- The second component shows the strong correlation with hardness and Density. Thus, the company can control the taste or quality or pastry-type food for instance, they can control the hardness of food by changing the second components.

## References
[1] Webite: Machine Learning co ban. Principal Component Analysis. June 15, 2017.

[2] Title: Principal Component Analysis Some Mathematical Backgrounds. Author: Arie
van Erk, BiGCaT. Date accessed 25.6.2021.

[3]Principle Component Analysis(PCA) Chapter 6.2 Geometric explanation of PCA. Date
Accessed: 25.6.2021

## About Us
Our project includes two contributors:
- Tran Xuan Loc - 18127131 - 18127131@student.hcmus.edu.vn
- Thai Hoang Huy - 18127109 - 18127109@student.hcmus.edu.vn
