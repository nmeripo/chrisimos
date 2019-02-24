# chrísimos

## Jupyter Notebook to Python Script
``` bash
jupyter nbconvert --to script model.ipynb
```

## Terminate Jupyter
sudo kill -9 $(lsof -i tcp:[your_port_number] -t)

## Detach and Run
nohup python -u model.py > model.out 2>&1
