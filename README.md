<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>学生评估报告</title>
    <style>
        body {
            font-family: 'Microsoft YaHei', sans-serif;
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .container {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .header {
            text-align: center;
            margin-bottom: 30px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            font-size: 16px;
        }
        input[type="text"], textarea, select {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
            font-size: 16px;
            background-color: white;
        }
        textarea {
            min-height: 150px;
            resize: vertical;
        }
        .photo-section {
            display: flex;
            align-items: start;
            gap: 20px;
            margin-bottom: 20px;
        }
        .photo-container {
            width: 150px;
            height: 200px;
            border: 2px dashed #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        .photo-container img {
            max-width: 100%;
            max-height: 100%;
            object-fit: cover;
        }
        .info-section {
            flex: 1;
        }
        .evaluation-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin: 30px 0;
        }
        select:focus {
            outline: none;
            border-color: #4a90e2;
        }
        .comment-section {
            margin-top: 30px;
            border-top: 2px solid #eee;
            padding-top: 20px;
        }
        optgroup {
            font-weight: bold;
            color: #666;
        }
        option {
            padding: 4px;
        }
        select {
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>学生评估报告</h1>
        </div>

        <form id="evaluationForm">
            <div class="photo-section">
                <div>
                    <div class="photo-container">
                        <img src="/api/placeholder/150/200" alt="学生照片">
                    </div>
                </div>
                
                <div class="info-section">
                    <div class="form-group">
                        <label for="studentName">学生姓名</label>
                        <input type="text" id="studentName" name="studentName">
                    </div>
                    <div class="form-group">
                        <label for="grade">年级</label>
                        <select id="grade" name="grade">
                            <option value="">请选择年级</option>
                            <option value="K1">K1 (5岁)</option>
                            <option value="K2">K2 (6岁)</option>
                            <option value="Y1">Y1 (7岁)</option>
                            <option value="Y2">Y2 (8岁)</option>
                            <option value="Y3">Y3 (9岁)</option>
                            <option value="Y4">Y4 (10岁)</option>
                            <option value="Y5">Y5 (11岁)</option>
                            <option value="Y6">Y6 (12岁)</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="subject">科目</label>
                        <select id="subject" name="subject">
                            <option value="">请选择科目</option>
                            <option value="BM">BM（国文理解）</option>
                            <option value="BMK">BMK（国文作文）</option>
                            <option value="BI">BI（英文理解）</option>
                            <option value="BIK">BIK（英文作文）</option>
                            <option value="BC">BC（华文理解）</option>
                            <option value="BCK">BCK（华文作文）</option>
                            <option value="MM">MM（数学）</option>
                            <option value="SC">SC（科学）</option>
                            <option value="overall">整体（整体表现）</option>
                        </select>
                    </div>
                </div>
            </div>

            <div class="evaluation-grid">
                <div class="form-group">
                    <label for="attention">专心度</label>
                    <select id="attention" name="attention">
                        <option value="">请选择专心度评估</option>
                        <optgroup label="⭐ 需要改进">
                            <option value="a1">⭐ 容易被外界干扰，难以保持专注</option>
                            <option value="a2">⭐ 单调或困难任务容易失去兴趣</option>
                            <option value="a3">⭐ 情绪波动时难以集中注意力</option>
                            <option value="a4">⭐ 对某些活动缺乏兴趣，难以集中</option>
                            <option value="a5">⭐ 身体状态影响导致无法专心</option>
                        </optgroup>
                        <optgroup label="⭐⭐ 表现尚可">
                            <option value="b1">⭐⭐ 多数时候能集中，偶尔受干扰</option>
                            <option value="b2">⭐⭐ 能专注完成任务，但有时分心</option>
                            <option value="b3">⭐⭐ 感兴趣时专注，困难任务易分心</option>
                            <option value="b4">⭐⭐ 能集中一段时间，偶有情绪影响</option>
                            <option value="b5">⭐⭐ 表现不错，偶尔需要提醒</option>
                        </optgroup>
                        <optgroup label="⭐⭐⭐ 表现优异">
                            <option value="c1">⭐⭐⭐ 持续保持专注，任务完成好</option>
                            <option value="c2">⭐⭐⭐ 专注持久，学习效率高</option>
                            <option value="c3">⭐⭐⭐ 专心度高，很少受干扰</option>
                            <option value="c4">⭐⭐⭐ 感兴趣的事能长时间专注</option>
                            <option value="c5">⭐⭐⭐ 通常专心，特殊情况除外</option>
                        </optgroup>
                    </select>
                </div>

                <div class="form-group">
                    <label for="participation">积极性</label>
                    <select id="participation" name="participation">
                        <option value="">请选择积极性评估</option>
                        <optgroup label="⭐ 需要改进">
                            <option value="p1">⭐ 较少主动回答问题或参与讨论</option>
                            <option value="p2">⭐ 需要多次提醒才会完成任务</option>
                            <option value="p3">⭐ 对学习活动兴趣不高</option>
                            <option value="p4">⭐ 课堂参与度较低</option>
                            <option value="p5">⭐ 作业完成态度被动</option>
                        </optgroup>
                        <optgroup label="⭐⭐ 表现尚可">
                            <option value="p6">⭐⭐ 经常能主动参与课堂活动</option>
                            <option value="p7">⭐⭐ 基本能按时完成作业</option>
                            <option value="p8">⭐⭐ 遇到问题会寻求帮助</option>
                            <option value="p9">⭐⭐ 对感兴趣的内容会积极参与</option>
                            <option value="p10">⭐⭐ 能配合老师完成教学活动</option>
                        </optgroup>
                        <optgroup label="⭐⭐⭐ 表现优异">
                            <option value="p11">⭐⭐⭐ 经常主动举手回答问题</option>
                            <option value="p12">⭐⭐⭐ 积极参与课堂讨论和活动</option>
                            <option value="p13">⭐⭐⭐ 认真完成每项作业任务</option>
                            <option value="p14">⭐⭐⭐ 遇到困难会主动寻求解决方法</option>
                            <option value="p15">⭐⭐⭐ 乐于帮助其他同学</option>
                        </optgroup>
                    </select>
                </div>

                <div class="form-group">
                    <label for="handwriting">字体整齐度</label>
                    <select id="handwriting" name="handwriting">
                        <option value="">请选择字体整齐度评估</option>
                        <optgroup label="⭐ 需要改进">
                            <option value="h1">⭐ 字迹潦草，难以辨认</option>
                            <option value="h2">⭐ 书写格式不规范</option>
                            <option value="h3">⭐ 作业本整洁度较差</option>
                            <option value="h4">⭐ 经常出现涂改痕迹</option>
                            <option value="h5">⭐ 字体大小不统一</option>
                        </optgroup>
                        <optgroup label="⭐⭐ 表现尚可">
                            <option value="h6">⭐⭐ 字迹基本清晰可辨</option>
                            <option value="h7">⭐⭐ 书写较为工整</option>
                            <option value="h8">⭐⭐ 作业本保持基本整洁</option>
                            <option value="h9">⭐⭐ 偶尔有涂改但整体整齐</option>
                            <option value="h10">⭐⭐ 多数时候能保持行文整齐</option>
                        </optgroup>
                        <optgroup label="⭐⭐⭐ 表现优异">
                            <option value="h11">⭐⭐⭐ 字迹工整清晰</option>
                            <option value="h12">⭐⭐⭐ 书写规范美观</option>
                            <option value="h13">⭐⭐⭐ 作业本非常整洁</option>
                            <option value="h14">⭐⭐⭐ 很少出现涂改</option>
                            <option value="h15">⭐⭐⭐ 版面布局合理规范</option>
                        </optgroup>
                    </select>
                </div>

                <div class="form-group">
                    <label for="performance">课堂表现</label>
                    <select id="performance" name="performance">
                        <option value="">请选择课堂表现评估</option>
                        <optgroup label="⭐ 需要改进">
                            <option value="c1">⭐ 经常走神或做与课堂无关的事</option>
                            <option value="c2">⭐ 较难遵守课堂纪律</option>
                            <option value="c3">⭐ 作业完成情况不稳定</option>
                            <option value="c4">⭐ 需要频繁提醒才能跟上进度</option>
                            <option value="c5">⭐ 与同学互动较少</option>
                        </optgroup>
                        <optgroup label="⭐⭐ 表现尚可">
                            <option value="c6">⭐⭐ 基本能跟随课堂节奏</option>
                            <option value="c7">⭐⭐ 遵守课堂基本纪律</option>
                            <option value="c8">⭐⭐ 能完成大部分课堂任务</option>
                            <option value="c9">⭐⭐ 与同学有正常互动</option>
                            <option value="c10">⭐⭐ 听从老师的指导和建议</option>
                        </optgroup>
                        <optgroup label="⭐⭐⭐ 表现优异">
                            <option value="c11">⭐⭐⭐ 全程积极投入课堂学习</option>
                            <option value="c12">⭐⭐⭐ 严格遵守课堂纪律</option>
                            <option value="c13">⭐⭐⭐ 出色完成各项课堂任务</option>
                            <option value="c14">⭐⭐⭐ 与同学积极互动合作</option>
                            <option value="c15">⭐⭐⭐ 对老师的指导反馈及时</option>
                        </optgroup>
                    </select>
                </div>
            </div>

            <div class="comment-section">
                <div class="form-group">
                    <label for="evaluation">教师评语</label>
                    <textarea id="evaluation" name="evaluation" placeholder="请输入对学生的评价..."></textarea>
                </div>
            </div>
        </form>
    </div>
  
