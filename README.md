# Student-Manager-Flask

基于 Flask + SQLite 的 Web 学生信息管理系统，响应式页面，支持注册登录、学生信息增删改查与多条件搜索。

## 功能特性

- 响应式 Web 页面，HTML 模板由 `render_template_string` 内联在 `app.py` 中，无需前端构建
- 用户注册、登录、登出（基于 Flask session）
- 学生信息新增、查询、修改、删除（REST 风格接口）
- 按姓名、学号、年龄多条件搜索
- SQLite 数据库 `student_management.db` 在首次启动时自动创建并建表，无需手动初始化

## 技术栈与依赖

- Python 3、Flask==2.3.3、sqlite3（标准库）
- 前端为内联 HTML / CSS / JavaScript，无打包或构建步骤
- 依赖见 `requirements.txt`：Flask==2.3.3

## 目录结构

```text
Student-Manager-Flask/
├── app.py             # 应用入口：路由、业务逻辑与内联 HTML 模板
├── requirements.txt   # Flask==2.3.3
├── .gitignore         # 忽略 __pycache__/、*.py[cod]、*.db 等
├── LICENSE            # MIT 许可证
└── README.md          # 本说明
```

## 快速开始

```bash
git clone https://github.com/RockyproJiang/Student-Manager-Flask.git
cd Student-Manager-Flask
pip install -r requirements.txt
python app.py
```

默认以 `host='0.0.0.0'`、`port=5000`、`debug=True` 启动，浏览器访问 `http://127.0.0.1:5000/`。首次运行自动创建 `student_management.db`。

## 配置与安全说明

- `FLASK_SECRET_KEY` 环境变量作为 Flask session 签名密钥；未设置时每次启动用 `secrets.token_hex(32)` 生成随机密钥，因此重启后旧登录态失效。原先硬编码的 `app.secret_key = '653-254-338'` 已移除。
- 数据库文件 `student_management.db` 自动创建，包含 `login_table` 与 `info_table`。
- **安全说明**：登录密码明文存于 `login_table.st_password` 并明文比对，仅用于本地学习演示，切勿用于生产环境、不要使用真实密码；正式使用应改为加盐哈希（如 bcrypt / argon2）。
- `host='0.0.0.0'` 与 `debug=True` 为开发默认值，生产环境请关闭调试、配合 WSGI 服务器与反向代理，并限制访问来源。
- 仓库已从版本库移除误提交的 `__pycache__`，并通过 `.gitignore` 忽略，`*.db` 等本地数据文件同样不会进入版本库。

## 许可证

本项目采用 MIT 许可证，详见 LICENSE。
