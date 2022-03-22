For MAC M1

1. Add a filter to git config by running the following command in bash inside the repo:  
```
git config filter.strip-notebook-output.clean 'jupyter nbconvert --ClearOutputPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR'  
```
2. Create a `.gitattributes` file inside the directory with the notebooks  

3. Add the following to that file:   
```
*.ipynb filter=strip-notebook-output  
```

After that, commit to git as usual. The notebook output will be stripped out in git commits, but it will remain unchanged locally.  

This gist is based on @dirkjot's answer to [this StackOverflow question](https://stackoverflow.com/questions/28908319/how-to-clear-an-ipython-notebooks-output-in-all-cells-from-the-linux-terminal/).