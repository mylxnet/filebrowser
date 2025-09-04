<p align="center">
  <img src="https://raw.githubusercontent.com/filebrowser/logo/master/banner.png" width="550"/>
</p>

[![Build](https://github.com/filebrowser/filebrowser/actions/workflows/main.yaml/badge.svg)](https://github.com/filebrowser/filebrowser/actions/workflows/main.yaml)
[![Go Report Card](https://goreportcard.com/badge/github.com/filebrowser/filebrowser)](https://goreportcard.com/report/github.com/filebrowser/filebrowser)
[![Documentation](https://img.shields.io/badge/godoc-reference-blue.svg)](http://godoc.org/github.com/filebrowser/filebrowser)
[![Version](https://img.shields.io/github/release/filebrowser/filebrowser.svg)](https://github.com/filebrowser/filebrowser/releases/latest)
[![Chat IRC](https://img.shields.io/badge/freenode-%23filebrowser-blue.svg)](http://webchat.freenode.net/?channels=%23filebrowser)

File Browser provides a file managing interface within a specified directory and it can be used to upload, delete, preview and edit your files. It is a **create-your-own-cloud**-kind of software where you can just install it on your server, direct it to a path and access your files through a nice web interface.

<code>
services:
  filebrowser:
    image: filebrowser/filebrowser    # 使用官方的 FileBrowser 镜像
    user: "0:0"                       # 指定以 root 用户运行容器（UID=0, GID=0）
    container_name: filebrowser       # 容器名称为 filebrowser，方便管理
    ports:
      - "8680:80"                     # 将宿主机的 8680 端口映射到容器的 80 端口
                                      # 浏览器访问 http://宿主机IP:8680 即可使用 FileBrowser
    volumes:
      - ./filebrowser_data:/srv       # 挂载数据目录，FileBrowser 的根目录，对应宿主机 ./filebrowser_data
      - ./filebrowser_database:/database  # 挂载数据库目录，存放用户账号、配置等信息
      - ./filebrowser_config:/config  # 挂载配置目录，存放 settings.json 等配置文件
    restart: always                   # 设置容器自动重启策略（异常退出后自动重启）

</code>


## Documentation

Documentation on how to install, configure, and contribute to this project is hosted at [filebrowser.org](https://filebrowser.org).

## Project Status

> [!WARNING]
>
> This project is currently on **maintenance-only** mode, and is looking for new maintainers. For more information, please read the [discussion #4906](https://github.com/filebrowser/filebrowser/discussions/4906). Therefore, please note the following:
>
> - It can take a while until someone gets back to you. Please be patient.
> - [Issues][issues] are only being used to track bugs. Any unrelated issues will be converted into a [discussion][discussions].
> - No new features will be implemented until further notice. The priority is on triaging issues and merge bug fixes.
> 
> If you're interested in maintaining this project, please reach out via the discussion above.

[issues]: https://github.com/filebrowser/filebrowser/issues
[discussions]: https://github.com/filebrowser/filebrowser/discussions

## Contributing

Contributions are always welcome. To start contributing to this project, read our [guidelines](CONTRIBUTING.md) first.

## License

[Apache License 2.0](LICENSE) © File Browser Contributors
