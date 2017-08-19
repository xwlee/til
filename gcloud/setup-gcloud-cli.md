Install the **gcloud** sdk
```shell
brew cask install google-cloud-sdk
```

Configure your **Google Cloud Platform (GPC)** account information. This should automatically open a browser from where we can log in to our Google Cloud account and authorize the SDK.
```shell
gcloud auth login
```

Get your PROJECT_ID of the project you want to set as default project
```
gcloud projects list
```

Set you project as the default project
```
gcloud config set project <PROJECT_ID>
```
