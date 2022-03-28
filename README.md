# India Summer Monsoon Rainfall (ISMR)

A case study using XCast to generate probabilistic forecasts of Indian Summer Monsoon Rainfall (ISMR) by creating Probabilistic Output Extreme Learning Machine (POELM)-based multi-model ensembles of the North American Multi-Model Ensemble (NMME). ISMR is characterized by intense rain over India onsetting around June, and receeding around September. For the purposes of this study we take May-initialized, Lead-1 forecasts of the JJAS season as predictors, and aggregated High-Resolution India Meteorological Department Daily Precipitation data as the predictand. 

We proceed by one-hot encoding the predictand using a scheme which translates the lowest 33% of data points to the "Below Normal" category, the highest 33% of data points to the "Above Normal" category, and all others to the "Near Normal" category. The predictors are then scaled to the interval [-1, 1] using MinMax Scaling, and a set of N randomly-initialized POELM models are fit, and used to make predictions. The N randomly-initialized results are then averaged to create an ensemble mean and address the non-determinism of the POELM approach. 

All of the above operations are performed on a gridpoint-wise basis, and within Leave-One-Year-Out cross-validation. Cross-validated hindcasts are compared with the observations data to compute skill scores. 

# Installing this repository: 

```
git clone https://github.com/kjhall01/monsoon.git
cd monsoon
conda create -c conda-forge -c hallkjc01 -n climate xcast xarray matplotlib pandas numpy cartopy jupyter
conda activate climate 
python -m ipykernel install --user --name=climate
jupyter notebook IndiaJJAS.ipynb
```

select kernel >> climate
then click "restart and run all cells" 
