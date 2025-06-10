# Artifact Appendix

Paper title: **Navigating Social Media Privacy: Awareness, Preferences, and Discoverability**

Artifacts HotCRP Id: **#18**

Requested Badge: **Reproduced**

## Description
This artifact provides anonymous survey data and a Python notebook to reproduce the results presented in the paper. 

## Security/Privacy Issues and Ethical Concerns
We remove all survey metadata and provide only participants' answers, ensuring that no sensitive data is disclosed. 

## Basic Requirements
No special hardware requirements (can run on a local laptop). 

## Software Requirements
We tested this artifact on MAC but it also can be run on Linux or Window as long as the platforms install Python 3.8.11 (recommended through [pyenv](https://github.com/pyenv/pyenv)) and [Jupyter Notebook](https://code.visualstudio.com/docs/datascience/jupyter-notebooks) (recommended through [VS Code](https://code.visualstudio.com/download)). 

## Estimated Time and Storage Consumption
The survey data (stored in [raw](./raw/)) is around 700KB and running the Python notebook ([artifact.ipynb](artifact.ipynb)) should complete within a few minutes. 

## Environment 
We run the artifact using Python 3.8.11, which we recommend installing via [pyenv](https://github.com/pyenv/pyenv). 

In short, on MAC run the following to install Python 3.8.11
```
brew update
brew install pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init - zsh)"' >> ~/.zshrc
exec "$SHELL"
pyenv install 3.8.11
pyenv local 3.8.11
```

If you are using Linux, replace the first two "brew" commands to
```
curl -fsSL https://pyenv.run | bash
```

The example above applies to Zsh as a shell. If you use other shells (e.g., Bash, Fish, etc.), please follow these [instructions](https://github.com/pyenv/pyenv?tab=readme-ov-file#b-set-up-your-shell-environment-for-pyenv) to set up your shell environment for pyenv. 

## Testing the Environment

Now that Python 3.8.11 is installed, we recommend setting up a virtual environment (venv) to install packages required to run the Python notebook. 

Run the following to set up the venv
```
python -m venv artifact_venv
source artifact_venv/bin/activate
pip install -r requirements.txt
```

The packages required ([requirements.txt](requirements.txt)) include numpy, pandas, matplotlib, statsmodels, and ipykernel. 

Now that the venv is created, make sure to select it (artifact_venv) as your kernel in your notebook. 

## Artifact Evaluation
Run (click "Run All") the Python notebook ([artifact.ipynb](artifact.ipynb)) to reproduce tables and plots in the paper. 

## Results
We reproduce ALL results presented in the paper. Please refer to the notebook ([artifact.ipynb](artifact.ipynb)) as we specify which code section reproduce which result. 

## Personal Notes
To reproduce the statistical analysis in Section 4.4 (Correlations), 4.5 (Demographic and Usage Differences), and 4.6 (Platform-specific Differences), we used the statsmodels package to generate all correlation (4.4) and regression results (4.5 and 4.6). Alternatively, you can download the dataframe df_stat as csv after it was preprocessed in **Demographic and usage differences (Section 4.5)** `df_stat.to_csv('stat_raw.csv', index=False)` and use this csv file with your stat software (e.g., SPSS) to run statistical analysis. We verified that the results produced with statsmodels and SPSS, are identical. 

## Question Number References

We provide mapping of question numbers to questions asked below. For each platform, we asked: 1. if users have seen a privacy setting $X$ (privacy_features_seen_questions), 2. if users are satisfied with the default setting of $X$ (privacy_features_default_questions), and 3. how hard for users to locate $X$ (privacy_features_find_questions). For 3., we also record how long in seconds users spend locating $X$ (privacy_features_time_questions). 
For each privacy setting $X$ available on each platform, please refer to Table 1 in the paper. 
For demographic and usage question number mapping, please refer to variables `demo_cols_encode` and `general_usage_cols_encode` in the notebook ([artifact.ipynb](artifact.ipynb)). 

```
privacy_features_seen_questions = {
    "Facebook": {
        "audience": "Q2.3", 
        "message": "Q2.5", 
        "ads": "Q2.7", 
        "activity_status": "Q2.9", 
        "account_suggestion": "Q2.11", 
        "connection_view": "Q2.13", 
        "profile": "Q2.15", 
        "search": "Q2.17"
    }, 
    "Instagram": {
        "audience": "Q2.3", 
        "message": "Q2.5", 
        "ads": "Q2.7", 
        "activity_status": "Q2.9", 
        "video": "Q2.11", 
    }, 
    "Twitter (X)": {
        "audience": "Q2.3", 
        "message": "Q2.5", 
        "ads": "Q2.7", 
        "account_suggestion": "Q2.9", 
        "video": "Q2.11", 
    }, 
    "LinkedIn": {
        "audience": "Q2.3", 
        "message": "Q2.5", 
        "ads": "Q2.7", 
        "activity_status": "Q2.9", 
        "account_suggestion": "Q2.11", 
        "connection_view": "Q2.13", 
        "search": "Q2.15", 
        "profile": "Q2.17"
    }, 
    "TikTok": {
        "audience": "Q2.3", 
        "message": "Q2.5", 
        "ads": "Q2.7", 
        "activity_status": "Q2.9", 
        "account_suggestion": "Q2.11", 
        "connection_view": "Q2.13", 
        "video": "Q2.15", 
    }, 
    "Snapchat": {
        "audience": "Q2.3", 
        "message": "Q2.5", 
        "ads": "Q2.7", 
        "activity_status": "Q2.9", 
        "account_suggestion": "Q2.11", 
    }
}

privacy_features_default_questions = {
    "Facebook": {
        "audience": "Q2.4", 
        "message": "Q2.6", 
        "ads": "Q2.8", 
        "activity_status": "Q2.10", 
        "account_suggestion": "Q2.12", 
        "connection_view": "Q2.14", 
        "profile": "Q2.16", 
        "search": "Q2.18"
    }, 
    "Instagram": {
        "audience": "Q2.4", 
        "message": "Q2.6", 
        "ads": "Q2.8", 
        "activity_status": "Q2.10", 
        "video": "Q2.12", 
    }, 
    "Twitter (X)": {
        "audience": "Q2.4", 
        "message": "Q2.6", 
        "ads": "Q2.8", 
        "account_suggestion": "Q2.10", 
        "video": "Q2.12", 
    }, 
    "LinkedIn": {
        "audience": "Q2.4", 
        "message": "Q2.6", 
        "ads": "Q2.8", 
        "activity_status": "Q2.10", 
        "account_suggestion": "Q2.12", 
        "connection_view": "Q2.14", 
        "search": "Q2.16", 
        "profile": "Q2.18"
    }, 
    "TikTok": {
        "audience": "Q2.4", 
        "message": "Q2.6", 
        "ads": "Q2.8", 
        "activity_status": "Q2.10", 
        "account_suggestion": "Q2.12", 
        "connection_view": "Q2.14", 
        "video": "Q2.16", 
    }, 
    "Snapchat": {
        "audience": "Q2.4", 
        "message": "Q2.6", 
        "ads": "Q2.8", 
        "activity_status": "Q2.10", 
        "account_suggestion": "Q2.12", 
    }
}

privacy_features_find_questions = {
    "Facebook": {
        "audience": "Q4.2", 
        "account_suggestion": "Q4.7", 
        "activity_status": "Q4.12", 
        "message": "Q4.17", 
        "profile": "Q5.2", 
        "connection_view": "Q5.7", 
        "ads": "Q5.12", 
        "search": "Q5.17"
    }, 
    "Instagram": {
        "audience": "Q4.2", 
        "activity_status": "Q4.7", 
        "ads": "Q4.12", 
        "message": "Q4.17", 
        "video": "Q4.22", 
    }, 
    "Twitter (X)": {
        "audience": "Q4.2", 
        "account_suggestion": "Q4.7", 
        "message": "Q4.12", 
        "ads": "Q4.17", 
        "video": "Q4.22", 
    }, 
    "LinkedIn": {
        "audience": "Q4.2", 
        "account_suggestion": "Q4.7", 
        "message": "Q4.12", 
        "activity_status": "Q4.17", 
        "profile": "Q5.2", 
        "connection_view": "Q5.7", 
        "ads": "Q5.12", 
        "search": "Q5.17", 
    }, 
    "TikTok": {
        "audience": "Q4.2", 
        "account_suggestion": "Q4.12", 
        "message": "Q4.7", 
        "activity_status": "Q5.17", 
        "connection_view": "Q5.2", 
        "ads": "Q5.7", 
        "video": "Q5.12", 
    }, 
    "Snapchat": {
        "audience": "Q4.2", 
        "message": "Q4.17", 
        "ads": "Q4.22", 
        "activity_status": "Q4.12", 
        "account_suggestion": "Q4.7", 
    }
}

privacy_features_time_questions = {
    "Facebook": {
        "audience": "Q4.1", 
        "account_suggestion": "Q4.6", 
        "activity_status": "Q4.11", 
        "message": "Q4.16", 
        "profile": "Q5.1", 
        "connection_view": "Q5.6", 
        "ads": "Q5.11", 
        "search": "Q5.16"
    }, 
    "Instagram": {
        "audience": "Q4.1", 
        "activity_status": "Q4.6", 
        "ads": "Q4.11", 
        "message": "Q4.16", 
        "video": "Q4.21", 
    }, 
    "Twitter (X)": {
        "audience": "Q4.1", 
        "account_suggestion": "Q4.6", 
        "message": "Q4.11", 
        "ads": "Q4.16", 
        "video": "Q4.21", 
    }, 
    "LinkedIn": {
        "audience": "Q4.1", 
        "account_suggestion": "Q4.6", 
        "message": "Q4.11", 
        "activity_status": "Q4.16", 
        "profile": "Q5.1", 
        "connection_view": "Q5.6", 
        "ads": "Q5.11", 
        "search": "Q5.16", 
    }, 
    "TikTok": {
        "audience": "Q4.1", 
        "account_suggestion": "Q4.11", 
        "message": "Q4.6", 
        "activity_status": "Q5.16", 
        "connection_view": "Q5.1", 
        "ads": "Q5.6", 
        "video": "Q5.11", 
    }, 
    "Snapchat": {
        "audience": "Q4.1", 
        "message": "Q4.16", 
        "ads": "Q4.21", 
        "activity_status": "Q4.11", 
        "account_suggestion": "Q4.6", 
    }
}
```

