# Random Forest Visualisation Tools

## About
These tools aim to provide a reproducible and consistent data visualisation platform where experimental and computational researchers can perform Random Forest (RF) to explore their data and perform regression tasks without requiring a line of code. Random Forest is a supervised machine learning model that learns to map data (features or descriptors) by constructing a multitude of decision trees to outputs (target variables) in the training phase of the model. It uses bagging and feature randomness when building each individual tree to try to create an uncorrelated forest of trees that predict target variables more accurately than a single decision tree.

### App Manual
- The app manual, explaining data file upload requirements, features of the tool and how to read the plot outputs can be found [here](https://aaml-analytics.github.io/rf-explorer/)

## Deploy app on server (production and development)

### Requirements
- Download [Python 3](https://www.python.org) if not already installed 
- Install [Git](https://git-scm.com/downloads) 
-- Installation instructions using command line can be found [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 
Note: If you are using Git after upgrading to macOS Catalina and get the following error...
```bash
xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
```
...run the following in your terminal:
```bash
xcode-select --install
```
- Install virtualenv to create virtual environments 
```bash
pip install virtualenv
```

### Running the app
To run this app first clone repository and then open a terminal to the app folder.
```bash
git clone https://github.com/aaml-analytics/rf-explorer/
cd rf-explorer
```

Create and activate a new virtual environment (recommended) by running the following:

On Windows:
```bash
virtualenv venv
\venv\scripts\activate
```

Or if using macOS or linux
```bash
python3 -m venv myvenv
source myvenv/bin/activate
```

Install the requirements:

```bash
pip install -r requirements.txt
```
#### Running the Random Forest App:
- When running a high number of iterations (n>=100), the development server is preferred. When running (n<=100) a production server is preferred. 
#### Run the app on development server:
```bash
python app.py
```
You can then run the app on your browser at http://127.0.0.1:8050
- To quit the app press (CTRL +C). You will have to run the app again with this command everytime you leave your terminal/ quit the app.

#### Run the app on production server by Gunicorn:
The suggested number of workers is (2*CPU)+1. For a dual-core (2 CPU) machine, 5 is the suggested workers value. The number of workers should equal the number of threads. The user can either use the below or change the worker and threads number accordingly.
```bash
gunicorn app:server --workers=5 --threads=5 --bind 0.0.0.0:8040
```
You can then run the app on your browser at http://0.0.0.0:8040


## Screenshots

![explorer-screenshot-1.png](explorer-screenshot-1.png)

## Contributing
When contributing to this repository, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change. You can also contact the AAML research group to discuss further contributions and collaborations. Please read [CONTRIBUTING.md](https://github.com/aaml-analytics/rf-explorer/blob/master/CONTRIBUTING.md) for details on our code of conduct.

## **Contact Us**
**Email**: 
[Mythili Sutharson](mailto:mls67@cam.ac.uk),
[Nakul Rampal](mailto:nr472@cam.ac.uk),
[Rocio Bueno Perez](mailto:rb901@cam.ac.uk),
[David Fairen Jimenez](mailto:df334@cam.ac.uk) <br>
**Website:** http://aam.ceb.cam.ac.uk/ <br>
**Address:** <br>
Department of Chemical Engineering and Biotechnology <br>
Cambridge University <br>
Philippa Fawcett Dr<br>
Cambridge <br>
CB3 0AS

## License
This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/aaml-analytics/rf-explorer/blob/add-license-1/LICENSE) file for details

## Acknowledgments
<p> 
  <img width=200 height=100 src="https://raw.githubusercontent.com/aaml-analytics/mof-explorer/master/MkDocs/A2ML-logo-dark.png">
</p>

- [AAML Research Group](http://aam.ceb.cam.ac.uk) for developing this dashboard for the MOF community. Click [here](http://aam.ceb.cam.ac.uk/research.html) to read more about our work
- [Dash](https://plot.ly/dash/) - the python framework used to build this web application

