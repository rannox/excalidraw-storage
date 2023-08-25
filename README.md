# excalidraw-storage-backend

This is the implementation of [excalidraw-storage-backend](https://github.com/alswl/excalidraw-collaboration). This version adds the possiblity to use a S3 backend for storing the excalidraw data. 

Feature:

- Storing scenes: when you export as a link
- Storing rooms: when you create a live collaboration
- Storing images: when you export or do a live collaboration of a scene with images

It use Keyv as a simple K/V store so you can use the database of your choice.
It also uses the AWS SDK, in order to store the data to an S3 compatible storage. 

## Environement Variables

| Name            | Description                                                  | Default value    |
| --------------- | ------------------------------------------------------------ | ---------------- |
| `PORT`          | Server listening port                                        | 8080             |
| `GLOBAL_PREFIX` | API global prefix for every routes                           | `/api/v2`        |
| `STORAGE_URI`   | [Keyv](https://github.com/jaredwray/keyv) connection string, example: `redis://user:pass@localhost:6379`. Availabe Keyv storage adapter: redis, mongo, postgres and mysql  | `""` (in memory **non-persistent**) |
| `LOG_LEVEL`     | Log level (`debug`, `verbose`, `log`, `warn`, `error`)       | `warn`           |
| `BODY_LIMIT`    | Payload size limit for scenes or images                      | ``               |
| `ENABLE_S3_BACKEND`    | Specify if S3 is to be used                      | `false`               |
| `EXCALIDRAW_S3_BUCKET_NAME`   | The S3 Bucket |
| `EXCALIDRAW_S3_ACCESS_KEY_ID`     | The S3 Access Key Id       | `warn`           |
| `EXCALIDRAW_S3_SECRET_ACCESS_KEY`    | The S3 Secret Access Key                      | ``               |
