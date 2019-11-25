![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 在所有表格和列中运行快速通配符搜索
#### Run A Quick SQL Wild Card Search Across All Tables And Columns
**发布-日期: 2016年02月24日 (评论)**

![#](images/##############?raw=true "#")

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
这是一些可以跨所有表和列执行通配符搜索的sql逻辑。在这个例子中，我正在寻找包含名称为“user”的列的所有表或视图。我为什么要这样做？这样我就可以深入了解应用程序中存储的用户信息类型。这在迁移时至关重要，这样你就可以确保迁移所有适当的用户。另外，这是为应用程序团队执行应用程序审计的好方法。


## English
Here’s some quick sql logic to perform a wild card search across all tables and columns. In this example I’m looking for any tables or views that contain a column with the name of ‘user’. Why am I doing this? So that I can drill down to see what kind of user information is stored in the application. This is essential when doing migrations so you can ensure that all the appropriate users are migrated. Additionally; it’s a great way to perform application auditing for the apps teams.

---
## Logic
```SQL
use mydb;
set nocount on
 
select
ist.table_type
,   isc.table_name
,   isc.column_name
from
information_schema.columns isc join information_schema.tables ist on isc.table_name = ist.table_name where
column_name like '%user%'
order by
table_name
,   column_name asc


```



[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

