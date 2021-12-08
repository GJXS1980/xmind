在文件夹外面创建 extract和build，把项目文件拷贝到extract：

```bash
mkdir extract
mkdir build
```

打包生成deb包：
```bash
dpkg-deb -b extract/ build/
```