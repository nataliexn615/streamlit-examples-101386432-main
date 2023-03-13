# streamlit-examples

## Streamlit and Its Use-Cases

This repository includes two beginner-level examples of using [Streamlit](https://github.com/streamlit/streamlit) which:

>Allow you to turn data scripts into shareable web apps in minutes, not weeks. It’s all Python, open-source, and free! And once you’ve created an app you can use our Community Cloud platform to deploy, manage, and share your app.

Using just Python, Streamlit allows a generation of both the back-end and the front-end of an online application or webpage. This means that by writing a few dozens lines of Python code, a developer can create an app that can be served to his colleagues at work, or to anyone across the world.

Streamlit can be limited in functionality and slow. Some of the notable limitations are its lack of design flexibility and control over the application layout. Moreover, if the application and/or dataset is large, there likely be speed issues. This is since the entire source code is being re-run on every new change or interaction.

Streamlit has proved useful for:
1. Serving data analytics dashboards when a user-interaction requires a backend (for instance to serve a model).
2. Presenting proof-of-concepts (POCs) of ML models


However, even with limited capabilities (compared to a backend and frontend built with e.g. Python and React), Streamlit can still allow making a large impact. 

### References
* [Streamlit Gallery](https://streamlit.io/gallery) - presents a wide collection of Streamlit apps. This is a great resource for inspiration and to get familiar with Streamlit's capabilities and limitations by example. 
* [Streamlit on Twitter](https://twitter.com/search?q=%23streamlit) - a (noisy) collection of more recent apps created with Streamlit.
* [Kilcommins, Medium](https://medium.datadriveninvestor.com/streamlit-everything-you-need-to-know-665eb90fcf4a) provides a thorough and critical review of Streamlit as of February 2021 (with many of the observations still relevant as of March 2023).

## Usage of this repository

1. Fork or Clone. Forking will be needed to serve the app from Streamlit Cloud
2. To run locally, run `python ./setup/setup.py` from the root folder of the repository (you can first read `/setup/README.md`, or go into the `setup.py` to see what it is doing)
3. Activate the virtual environment for the app you'd like to run
4. Run `streamlit run APP-FILE-NAME` from the root (where e.g. `APP-FILE-NAME=./hello_world/streamlit_hello_world.py`). This will start the app locally on your laptop. To stop the app press `ctrl-c` on `Windows` and `Linux`, or `cmd-c` on Mac in the terminal from which you launched the app. 
5. To serve the app from your own repository, go to [Streamlit Cloud](https://streamlit.io/cloud) and follow the instructions.

## Notes
* The repository includes two apps, each with its own Python package dependencies. The `Streamlit Cloud` service hosts each app independently, with its own Python environment. For multiple apps within a single repository, `Streamlit Cloud` assigns an environment to an app, based on a `requirements.txt` file that is in the app's folder ([docs](https://docs.streamlit.io/streamlit-community-cloud/get-started/deploy-an-app/app-dependencies)).
