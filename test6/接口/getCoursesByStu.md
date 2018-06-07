# 接口：getCoursesByStu  [返回](../README.md)
用例： [学生选课列表](../用例/学生选课列表.md)

- 功能：
   根据学生的学号专业和选择的学期显示老师可选择的教授课程列表。
    
- 权限：
    学生。    
    
- API请求地址： 
    接口基本地址/v1/api/getCoursesByStu

- 请求方式：
    GET

- 请求实例：

        {
            "students_id": "201510414128"
            "major": "软件（本）15-1"
            "term_id": "2017-2018第一学期"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |students_id|学生学号|
  |type|用户类型，此处为老师|
  |term_id|开课学期|
  |major|学生专业班级||
  * 注：只能由"学生"访问，因为"老师"无场景访问此接口。
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                "courses": [{
                    "course_id": "04470122"
                    "course_name_teachers": "系统分析与设计，授课老师：赵卫东"
                    "term_id": "2017-2018学年第1学期"
                    "techer_id": "123456"
                },{
                    "course_id": "04470121"
                    "course_name_teachers": " linux程序设计，授课老师：黄荣兵"
                    "course_term": "2017-2018学年第1学期"
                    "techer_id": "123456"
                }]   
            }    
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |courses|返回符合条件的所有课程集合，若空则返回[]|
  |course_id|课程编号|
  |course_name_teachers|老师授课课程名字|  
  |term_id|开课学期|
  |students_id|学生学号|
  |major|学生专业班级|
