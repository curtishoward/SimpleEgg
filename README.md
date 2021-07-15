## SimpleEgg 

Simple CDE PySpark example using a custom Python dependency.

#### Using .egg

Build the .egg:
```python setup.py bdist_egg```

Run the example:
```cde spark submit main.py --py-file ./dist/SimpleEgg-0.1-py3.7.egg --python-version python3```

#### Using penv

The __SimpleEgg__ dependency is defined in [requirements.txt](./requirements.txt).

Build the .whl and upload to the PyPI server (pypi.org in this case - [https://pypi.org/project/SimpleEgg/](https://pypi.org/project/SimpleEgg/)):
```python setup.py bdist_whl```

Run the job 
```
cde resource create --name penv-resource --python-version python3 --type python-env
cde resource upload --name penv-resource --local-path requirements.txt
cde spark submit main.py --python-env-resource-name penv-resource --python-version python3
```
