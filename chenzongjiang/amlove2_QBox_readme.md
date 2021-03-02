
# ![Qbox logo](http://otwcctfiu.bkt.clouddn.com/logo-blue.png)


> QBox is a convenient manage tool for your [Qiniu](https://www.qiniu.com/) buckets. It is an open-source software and can be used on `OS X`, `Linux` and `Windows`, and it was generated with [electron-vue](https://github.com/SimulatedGREG/electron-vue)

## Screenshots

#### Bucket Panel

![bucket panel](http://otwcctfiu.bkt.clouddn.com/bucket-panel.png)

#### Manage Panel

![bucket panel](http://otwcctfiu.bkt.clouddn.com/manage-panel.png)

#### Upload Panel

![bucket panel](http://otwcctfiu.bkt.clouddn.com/upload-panel.png)

## Feature

#### Bucket Panel

- [x] Login by setting `accessKey` and `secretKey`.
- [x] Logout by clearing localStorage (include `accessKey` and `secretKey`).
- [x] List all buckets (include private).
- [x] Manage files in a bucket, that will open a new `Manage Panel`.

#### Manage Panel

- [x] List all files in a specified bucket.
- [x] List all files with pagination.
- [x] Sort by `file name`, `file type`, `file size` or `modified time`.
- [x] Preview `image` and `media` file.
- [x] Delete a existing file.
- [x] Delete a batch of files were checked.
- [x] Copy the outer link of a file.
- [x] Refresh the files in the bucket.
- [x] Download a existing file.(this feature will be put in `preview` modal)
- [x] Upload a single file. 
- [x] Search filter.

## TODO

#### MenuBar

- [ ] Set default bucket.
- [ ] Drag to MenuBar icon to upload.

#### Bucket Panel

- [ ] Delete a existing bucket.
- [ ] Create a new bucket.

#### Manage Panel

- [x] Add enter event to search box.
- [ ] Upload mutiple files.
- [ ] Download a batch of files were checked.
- [ ] Rename resouces.

## License

[AGPL](https://github.com/LanceGin/QBox/blob/master/LICENSE)

## Contribute

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:9080
npm run dev

# build electron application for production
npm run build

# run unit tests (no tests now)
npm test

# lint all JS/Vue component files in `src/`
npm run lint
```

## [中文文档](https://github.com/LanceGin/QBox/blob/master/README_zh.md)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)