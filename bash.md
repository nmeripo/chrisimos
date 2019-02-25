#### Jupyter Notebook to Python Script
```bash
jupyter nbconvert --to script [your_notebook.ipynb]
```

#### Terminate Jupyter
```bash
sudo kill -9 $(lsof -i tcp:[your_port_number] -t)
```

#### Detach and Run
```bash
nohup python -u [your_script.py] > [your_logfile.out] 2>&1
```
#### Count number of files in a directory
```bash
ls -1 | wc -l
```

