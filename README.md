* Stachification Station

This is a basic proof of concept app that will allow users to upload a photo and have it stachified.

The basic process is
1. User uploads photo, which is saved to S3
2. Another python script grabs the file from S3, send it to Amazon's Rekongition API, adds a mustache, and saves it in S3 bucket
3. The Flask app displays the stached image
4. The Flask app empties the S3 bucket that stores uploads.

** Local Development

Before you start, you'll need to create an S3 bucket and provide credentials in your development environment.
I used a `.env` file. There's a sample .env file located at the root directory of this project, in case you
want an example.

For directions on CORS config, feel free to consult the toturial mentioned in the
Contributors section of this README.

Once you have the dependencies installed, run the following command in terminal:

```
$ export FLASK_APP=app.py # or put this in your .env file
$ flask run
```

In your browser, nagivate to `localhost:5000/` to see the site.


** Contributors

This codebase was begun by cobbling together info from the [Flask Quickstart Guide](http://flask.pocoo.org/docs/0.12/quickstart/)
and this [S3 direct upload tutorial](https://devcenter.heroku.com/articles/s3-upload-python).

In other words, if you're reading this, then you probably know more about Python and Flask best practices than I do.
So feel free to modify, remove, or add any code you feel is necessary.