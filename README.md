/* style.css */
:root {
  /* 颜色变量 */
  --primary-color: #2563eb;       /* 主色调 */
  --secondary-color: #3b82f6;     /* 次色调 */
  --text-color: #1e293b;          /* 主要文字颜色 */
  --background-gradient: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%); /* 背景渐变 */
  --input-border: #cbd5e1;        /* 输入框边框 */
  --input-focus: #93c5fd;         /* 输入框聚焦 */
  --shadow-color: rgba(0, 0, 0, 0.1); /* 阴影颜色 */
  --transition-speed: 0.3s;       /* 过渡速度 */
}

/* 基础重置 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 62.5%; /* 1rem = 10px */
  font-family: 'Inter', system-ui, -apple-system, sans-serif;
}

body {
  min-height: 100vh;
  display: grid;
  place-items: center;
  padding: 2rem;
  background: var(--background-gradient);
  color: var(--text-color);
  line-height: 1.5;
}

/* 登录容器 */
.login-container {
  width: 100%;
  max-width: 48rem;
  background: rgba(255, 255, 255, 0.95);
  padding: 4rem;
  border-radius: 1.6rem;
  box-shadow: 0 1rem 2.5rem var(--shadow-color);
  backdrop-filter: blur(1rem);
  border: 1px solid rgba(255, 255, 255, 0.3);
  transition: transform var(--transition-speed) ease;
}

.login-container:hover {
  transform: translateY(-0.5rem);
}

/* 标题样式 */
.login-header {
  text-align: center;
  margin-bottom: 4rem;
}

.login-title {
  font-size: 3.2rem;
  font-weight: 700;
  color: var(--primary-color);
  margin-bottom: 1rem;
  letter-spacing: -0.05em;
}

.login-subtitle {
  font-size: 1.6rem;
  color: #64748b;
}

/* 表单元素 */
.form-group {
  margin-bottom: 2.4rem;
  position: relative;
}

.form-label {
  display: block;
  font-size: 1.4rem;
  font-weight: 500;
  margin-bottom: 0.8rem;
  color: #475569;
}

.form-input {
  width: 100%;
  padding: 1.2rem 1.6rem;
  font-size: 1.6rem;
  border: 2px solid var(--input-border);
  border-radius: 0.8rem;
  transition: all var(--transition-speed) ease;
  background: #fff;
}

.form-input:focus {
  outline: none;
  border-color: var(--input-focus);
  box-shadow: 0 0 0 3px rgba(147, 197, 253, 0.3);
}

/* 第三方登录按钮 */
.social-login {
  margin: 3rem 0;
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}

.social-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  padding: 1.2rem;
  border: none;
  border-radius: 0.8rem;
  font-size: 1.4rem;
  font-weight: 500;
  cursor: pointer;
  transition: 
    transform var(--transition-speed) ease,
    opacity var(--transition-speed) ease;
}

.social-btn:hover {
  transform: translateY(-2px);
  opacity: 0.9;
}

.social-btn:active {
  transform: translateY(0);
}

.social-btn svg {
  width: 2rem;
  height: 2rem;
  margin-right: 1rem;
}

.google-btn {
  background: #fff;
  color: #374151;
  border: 1px solid #e5e7eb;
}

.github-btn {
  background: #24292e;
  color: #fff;
}

/* 辅助链接 */
.helper-links {
  text-align: center;
  margin-top: 3rem;
}

.link {
  color: var(--primary-color);
  text-decoration: none;
  font-size: 1.4rem;
  transition: color var(--transition-speed) ease;
}

.link:hover {
  color: var(--secondary-color);
  text-decoration: underline;
}

.link + .link {
  margin-left: 1.5rem;
}

/* 错误提示 */
.error-message {
  color: #dc2626;
  font-size: 1.4rem;
  margin-top: 1.5rem;
  padding: 1rem;
  background: #fee2e2;
  border-radius: 0.6rem;
  display: none;
  animation: slideIn 0.3s ease-out;
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 响应式设计 */
@media (max-width: 576px) {
  .login-container {
    padding: 3rem;
    margin: 2rem;
  }

  .login-title {
    font-size: 2.8rem;
  }

  .form-input {
    font-size: 1.4rem;
  }
}

@media (prefers-color-scheme: dark) {
  :root {
    --text-color: #f8fafc;
    --background-gradient: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
    --input-border: #334155;
    --input-focus: #60a5fa;
  }

  .login-container {
    background: rgba(30, 41, 59, 0.95);
    border-color: rgba(255, 255, 255, 0.1);
  }

  .google-btn {
    background: #334155;
    color: #fff;
    border-color: #475569;
  }
}
