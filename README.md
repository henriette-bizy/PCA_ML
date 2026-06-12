# PCA from Scratch — Education in Africa

This is our implementation of Principal Component Analysis (PCA) for the Advanced Linear Algebra
formative assignment. The whole thing is built from scratch using only NumPy for the maths and
Matplotlib for the plots — no sklearn anywhere.

The idea of the project is to take an education dataset covering African countries, which has 12
columns, and use PCA to reduce it down to just a couple of dimensions while keeping as much of the
information as possible. Along the way we standardize the data, build the covariance matrix, do the
eigendecomposition by hand, sort the components, pick how many to keep based on explained variance,
and finally project the data onto them.

## The data

We used the "Education in Africa" dataset from Kaggle:
https://www.kaggle.com/datasets/lydia70/education-in-africa

It has 12 columns and 756 rows, covering 54 African countries between 2010 and 2023.

We picked it because it ticks all the boxes the assignment asked for:

- it's African and focused on something that matters (education indicators)
- it has more than 7 columns (12)
- it has missing values — though these are hidden as the text `#N/B` rather than left blank
- it has a non-numeric column (`Country`)
- it isn't a generic dataset like house prices or wine quality

One thing worth pointing out: the missing values don't show up as blanks, they show up as the
string `#N/B`. So when loading the file we tell pandas to treat those as real missing values:

```python
pd.read_csv("file.csv", na_values=["#N/B", "..", "N/A", ""])
```

## What we did

- **Task 1** — implemented PCA: standardization, covariance matrix, eigendecomposition,
  sorting the eigenvectors by their eigenvalues, and projecting the data.
- **Task 2** — chose the number of principal components based on how much variance they explain,
  and explained the tradeoff and what information gets lost.
- **Task 3** — made the implementation faster so it can handle bigger datasets.

## Running it

1. Download the CSV from the Kaggle link above.
2. Open `[your_notebook_name].ipynb` in Google Colab or Jupyter.
3. Put the CSV in the same folder as the notebook (or change the path in the loading cell).
4. Run the cells top to bottom. Every cell shows its output, including the plots.

You'll need Python with NumPy, Matplotlib and pandas (pandas is just for loading and cleaning).

## What's in the repo

- `[your_notebook_name].ipynb` — the completed notebook
- `README.md` — this file
- `[contribution_sheet].pdf` — the contribution sheet
- `[combined_submission].pdf` — the notebook and contribution sheet combined into one PDF

## Results

(We'll fill this in once everything is run.)

- Number of components kept: `[N]`
- Variance retained: `[XX]%`
- Why we chose this number / the tradeoff: `[explanation]`
- What information is lost when reducing the dimensions: `[explanation]`

## Team

- Peer Pair Number: `[number]`
- `[Member 1 name]`
- `[Member 2 name]`