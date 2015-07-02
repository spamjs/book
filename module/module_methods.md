# Module Methods


|Signature| MODULE.parent() |
| -- |
| returns | parent  Module it is extended from|

|Signature| MODULE.getPath(path) |
| -- |
| returns | actual url of path relative to current MODULE |

|Signature| MODULE.load(path,data) |
| -- |
| returns | Prmoise to content of response |
| example 1 | MODULE.load("~my/path/file.json!json") <br/> actual request url will be relative to CONTEXT_PATH and data wil be served as json |
| example 2 | MODULE.load("/my/path/to/api!json") <br/> actual request url will be relative to website and data wil be served as json |
| example 3 | MODULE.load("/my/path/to/api!json",{qty :2}) <br/> actual request url will be relative to website and data wil be served as json |
| example 4 | MODULE.load("my/path/to/api",{qty :2}) <br/> actual request url will be relative to current module and data wil be served as string |


|Signature| MODULE.instance() |
| -- |
| returns | Creates new instance of that Module |
