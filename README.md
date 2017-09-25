# Mini Remote Downloader
A simple web app to help you download files on server, it's like a proxyed downloader, useful when certain sites are blocked.
Built with as little dependencies as possible.

## Deploy

0. Clone this repo
    ```
    git clone https://github.com/aulphar/remote-downloader.git
    ```

1. Replace placeholders for userName, password, and output directory
    ```
    return username == '{UserName}' and password == '{Password}'
    PATH_TO_SAVE = "{PATH}"
    ```
    
2. Start python app
    ```
    python app.py
    ```
    
## Usage
To start downloading simply make `POST` request on server with JSON looking like this:
```
{
    "url": "http://example.com",     // url to be downloaded
    "name": "example" [optional],    // new name of downloaded file
    "category": "example" [optional] // subfolder in downloads folder
}
``` 
And also use `Authorization` header with same `{UserName}` and `{Password}` you set in `app.py`

If dowloading started successfully Status code **`200`** will be returned, otherwise Status code will be **`409`** with actual error message in `JSON`.

## TODO

- Add support for downloading videos from Youtube
- Add support for downloading videos from OpenLoad