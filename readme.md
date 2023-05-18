# Sync AWS S3

The ideia for this repo is show how can be simple sync our files with a AWS S3 bucket.

The code bellow will get all files inside the folder `files` and put them in our bucket.  

Because the options `--delete` if we delete some file locally this will reflect in our bucket

```bash
    docker run --rm -ti \
        -v $(pwd):/aws \
        -e AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID \
        -e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY \
        amazon/aws-cli:2.11.20 \
        s3 sync ./files s3://my-bucket/ --delete
```
