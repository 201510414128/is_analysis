# 接口：getCourses  [返回](../README.md)
用例： [显示个人课程列表](../用例/个人课程列表.md)

- 功能：
   <br>1.根据type类型，判断Users类型为老师或学生<br/>
   2.学生根据学期显示学生的课程列表。<br/>
   3.老师根据学期显示老师的授课列表。<br/>
- 权限：
    学生。    
    
- API请求地址： 
    接口基本地址/v1/api/getCourses

- 请求方式：
    GET

- 请求实例：
<br/>type：teachers

       {
            "teachers_id": "201510414128",
            "term_id": "2017-2018学年第1学期"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |teachers_id|老师编号|
  |term_id|授课学期，格式必须固定|
  
<br/>type：students

       {
            "student_id": "201510414128",
            "term_id": "2017-2018学年第1学期"
        }
                
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学生学号|
  |term|学生所修的学期，格式必须固定|

  
- 返回实例：
<br/>type：students

        { 
            "status": true,
            "info": null,
            "data": {
                "courses": [{
                    "course_id": "04470122",
                    "course_name": "系统分析与设计",
                    "course_term": "2017-2018学年第1学期"
                },{
                    "course_id": "04470121",
                    "course_name": " linux程序设计",
                    "course_term": "2017-2018学年第1学期"
                    }
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
  |course_name|课程名称|  
  |teacher|老师信息|
  |teacher_id|老师编号|
  |teacher_name|老师姓名|
  
  <br/>type：students
  
          { 
              "status": true,
              "info": null,
              "data": {
                  "courses": [{
                      "course_id": "04470122",
                      "course_name_teachers": "系统分析与设计，授课老师：赵卫东",
                      "course_term": "2017-2018学年第1学期"
                  },{
                      "course_id": "04470121",
                      "course_name_teachers": " linux程序设计，授课老师：黄荣兵",
                      "course_term": "2017-2018学年第1学期"
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
    |course_name_teachers|课程名称|  
    |students|学生信息|
    |students_id|学生学号|
    |term_id|开课学期|

