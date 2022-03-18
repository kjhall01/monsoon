# monsoon
India Summer Monsoon Rainfall

# To set up: 

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
