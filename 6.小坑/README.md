# 小坑

```
[Err] 1055 - Expression #1 of ORDER BY clause is not in GROUP BY clause and contains nonaggregated column 'information_schema.PROFILING.SEQ' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql_mode=only_full_group_by
```
解决办法

```
set @@sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';
```
参考: https://www.cnblogs.com/skymyyang/p/7551646.html
##  Required request body is missing


```
@RequestBody不支持@GetMapping注解
```
### ERROR in static/js/vendor.666a349cafd8725e85b9.js from UglifyJs
Unexpected token: name (Dom7) [./node_modules/.2.0.1@dom7/dist/dom7.modular.js:14,0][static/js/vendor.666a349cafd8725e85b9.js:21192,6]

"vue-awesome-swiper": "^2.5.0", // 3.03 ==> 2.5.0 //https://github.com/nolimits4web/Swiper/issues/2263


