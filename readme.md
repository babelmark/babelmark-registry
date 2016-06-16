# Registry for babelmark

This repository contains the [registry](https://github.com/babelmark/babelmark-registry/blob/master/registry.json) for [babelmark](https://babelmark.github.io)

> NOTE: If you want to register an encrypted URL, send me an email at /alexandre_mutel at live dot com/ and I will return you an encrypted URL that you can send via a PR.
> If your service is enough secure (limiting < 1000 characters) and throttling, you can send plain url in the PR if you want.

An entry in the registry is composed like this:

* The name of the processor (can contain a version or additional infos)
* **url**: The url (encrypted or not, see the NOTE below) that will return the translation from markdown to html of the query `text=INSERT_MARKDOWN_HERE`. See below the format of the return of the query.
* **lang**: The language used to build the processor
* **repo**: A link to a repository or home page of the project

Example:
```json
{
"Name": "markdig",
"Url": "Xur5K1qwlgGyuSQSMsrcbfP7cdhSE9GrOZn+kDJqHuVJn44sZHZpFI7KMVQWyFzN3GVy0hqJTx5VKnLtSGYDdu95sk71j0WXxDBJU9kamXg=",
"Lang": "C#",
"Repo": "https://github.com/lunet-io/markdig/"
}
```

The query url must respond to a `http get`request to translate a markdown fragment to html. It must return a json that contains the result of the conversion: 

Query:
```
http://your.website.url.com/api/to_html?text=hi
```

Result:
```json
{"name":"markdig","html":"<p>hi</p>","version":"0.2.1"}
```

## Author

Alexandre MUTEL aka [xoofx](http://xoofx.com)


