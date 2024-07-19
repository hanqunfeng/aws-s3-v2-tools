# AWS S3 工具类

## 使用示例
* maven依赖
```xml
<dependency>
  <groupId>com.hanqunfeng</groupId>
  <artifactId>aws-s3-v2-tools</artifactId>
  <version>{latest-version}</version>
</dependency>
```

* gradle依赖
```groovy
implementation 'com.hanqunfeng:aws-s3-v2-tools:{latest-version}'
```

* 代码示例
```java
S3ClientConfig config = new S3ClientConfig("REGION", "AWS_ACCESS_KEY", "AWS_SECRET_KEY");

S3AsyncClient s3AsyncClient = S3ClientFactory.getInstance(config).getS3AsyncClient();
AmazonS3CRTV2Util.multipartUpload(s3AsyncClient, "BUCKET_NAME", remoteFileName, filePath, true);


S3TransferManager transferManager = S3ClientFactory.getInstance(config).getS3TransferManager();
AmazonS3TransferV2Util.uploadFile(transferManager, "BUCKET_NAME", remoteFileName, filePath);

S3Client s3Client = S3ClientFactory.getInstance(config).getS3Client();
//分段下载
AmazonS3V2Util.downloadSubsection(s3Client, "BUCKET_NAME", remoteFileName, outPath);
```
