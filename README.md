# mongo-backup-s3

Backup Mongo to S3 (supports mutli files)

## Basic usage

```sh
$ docker run -e S3_ACCESS_KEY_ID=key -e S3_SECRET_ACCESS_KEY=secret -e S3_BUCKET=my-bucket -e S3_PREFIX=backup -e MONGO_USER=user -e MONGO_PASSWORD=password -e MONGO_HOST=localhost registry.sendify.se/mongo-backup-s3
```

## Environment variables

- `MONGODUMP_OPTIONS` mongodump options (default: )
- `MONGO_DATABASE` list of databases you want to backup
- `MONGO_HOST` the mongo host *required*
- `MONGO_PORT` the mongo port (default: 3306)
- `MONGO_USER` the mongo user *required*
- `MONGO_PASSWORD` the mongo password *required*
- `S3_ACCESS_KEY_ID` your AWS access key *required*
- `S3_SECRET_ACCESS_KEY` your AWS secret key *required*
- `S3_BUCKET` your AWS S3 bucket path *required*
- `S3_PREFIX` path prefix in your bucket (default: 'backup')
- `S3_REGION` the AWS S3 bucket region (default: us-west-1)
- `S3_ENDPOINT` the AWS Endpoint URL, for S3 Compliant APIs such as [minio](https://minio.io) (default: none)
- `S3_S3V4` set to `yes` to enable AWS Signature Version 4, required for [minio](https://minio.io) servers (default: no)
- `MULTI_FILES` Allow to have one file per database if set `yes` default: no)