
# 接口：setOneStudentResults  [返回](../README.md)
用例： [评定成绩](../用例/评定成绩.md)

- 功能：
    设置一个学生的部分实验成绩和评语。
    
    输入参数result不为空，自动设置update_date为当前日期，表示同时设置批改日期。
    
    输入参数result为空，自动设置update_date为空，表示未批改。
    
- 权限：
    老师：可以查看所有学生的成绩。
    
- API请求地址： 
    接口基本地址/v1/api/etOneStudentResults

- 请求方式 ：
    POST
 
- 请求实例：  
        
        { 
            "student_id": "201510414128", 
            "total": 6,
            "data":[
                {
                "test_id":1,
                "test_score": 91, 
                test_score_part1:90,
                MEMO_part1:代码清晰,
                test_score_part2:92,
                MEMO_part2:代码清晰,
                ...其他评分项 
                "memo":"本实验做得好",
                }, 
                {
                ...其他实验
                }
            ]
        }

- 请求参数说明:       
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学号|
  |total|本次批改的所有实验的总数，小于等于全部实验的总数|
  |data|实验的成绩和评语|
  |test_id|实验编号|
  |memo|本实验老师的评价，可以为空|   
  |test_score| 分数，这个值为空表示没有批改|
  |test_score_part|单评分项分数，这个值为空表示没有批改|
  |MEMO| 老师对实验的评语|
  |MEMO_part|老师对某实验评分项的评语|
  |UPDATE_DATE|DATE|老师批改某实验的日期，为空表示未批改|
- 返回实例：

        {         
            "status": true,
            "info": null
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|


