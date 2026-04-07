# 学生管理系统

一个基于 Flask 的学生信息管理系统，支持学生信息的增删改查和用户认证功能。

## 功能特点

- 🔐 用户注册与登录
- 📝 学生信息的增删改查
- 🔍 多条件搜索（姓名、学号、年龄）
- 📱 响应式设计，支持移动端
- 💾 SQLite 数据库存储

## 技术栈

- 后端：Flask (Python)
- 前端：HTML5 + CSS3 + JavaScript
- 数据库：SQLite

## 安装与运行

### 1. 克隆项目

```bash
git clone https://github.com/yourusername/student-management-system.git
cd student-management-system
```

### 2. 安装依赖
pip install -r requirements.txt


### 3. 运行应用
python app.py

### 4. 访问应用
打开浏览器访问：http://localhost:5000

**使用说明**
>首次使用需要注册账号
    登录后可以查看学生列表
    点击"添加学生"按钮添加新学生
    点击"编辑"按钮修改学生信息
    点击"删除"按钮删除学生
    使用搜索功能快速查找学生

**项目结构**
student-management-system/
├── app.py              # 主应用程序
├── requirements.txt    # 依赖包列表
├── .gitignore         # Git忽略文件
└── README.md          # 项目说明文档

**注意事项**
- 生产环境请修改 app.secret_key
- 数据库文件会自动创建在项目根目录
- 默认运行在 5000 端口