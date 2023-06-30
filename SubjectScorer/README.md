"""
中文主观题批改模型
"""
from SubjectScorer import cSubjectScorer

input = '{"userId": "12345", "gradeType": 8, "questionId": "3394713", "question": "None", ' \
        '"maxScore": 3.0, "stdScore": 2, "userAnswerContent": [{"id": 0, "text": "用了比喻的修辞' \
        '手法，把小河比作镜、绸、母亲，写出了 小河的喜爱之情。"}], "rightAnswerContent": [{"id": 0, "' \
        'text": "画线句子使用了比喻的手法。将河水比作明镜和绸缎，流水声比作母亲的呢喃，生动形象地写出了秦岭' \
        '自然风光美丽动人，", "score": 1.0, "keyWord": ""}, {"id": 1, "text": "为下文小女孩的出场作' \
        '铺垫。", "score": 1.0, "keyWord": ""}, {"id": 2, "text": "表达了作者漫步秦岭时的愉悦心情，' \
        '表现了秦岭深处美好的景色。 ", "score": 1.0, "keyWord": ""}]}'
"""
输入主观题的json字符串，进行打分，打分后输出json字符串
"""

output = cSubjectScorer.Score(input)
print(output)


"""
--正常输出结果
{"totalScore": 1, "userAnswerContent": [{"id": 0, "text": "用了比喻的修辞手法，
把小河比作镜、绸、母亲，写出了 小河的喜爱之情。", "score": 1.0, "matchedAnswerInfo": 
["画线句子使用了比喻的手法。将河水比作明镜和绸缎，流水声比作母亲的呢喃，生动形象地写出了秦岭自然风光美丽动人，"]}]}
返回的code与msg

300034020 succes                   调用成功
300034021 init failed              初始化失败
300034022 input json is not valid  输入解析失败
300034023 score failed             批改失败        
