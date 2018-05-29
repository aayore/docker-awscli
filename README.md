# docker-awscli

Lightweight, transparent AWS CLI Docker image

## Usage

You need to feed credentials to the container:

`docker run -e AWS_ACCESS_KEY_ID="${AWS_ACCESS_KEY_ID}" -e AWS_SECRET_ACCESS_KEY="${AWS_SECRET_ACCESS_KEY}" aayore/docker-awscli aws s3 ls`

or

`docker run -v ~/.aws:/root/.aws aayore/docker-awscli aws s3 ls`

---

If you want to transfer any data, you'll have to mount the local directory:

`docker run -v ~/.aws:/root/.aws -v /your_data:/data aayore/docker-awscli aws s3 sync /data s3://your_bucket`
