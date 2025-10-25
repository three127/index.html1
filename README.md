<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>吴仲贤 - 物联网工程师</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #ffffff;
            --secondary-color: #e0e0e0;
            --accent-color: #6c63ff;
            --card-bg: rgba(40, 40, 40, 0.8);
            --card-bg-light: rgba(51, 51, 51, 0.7);
            --transition: all 0.3s ease;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Roboto', 'Noto Sans SC', sans-serif;
            background-color: #000;
            color: var(--primary-color);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* 背景样式 */
        .stars-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            background: url('https://lf3-static.bytednsdoc.com/obj/eden-cn/0077eh7fd/pngtree-pure-black-starry-minimalist-dreamy-business-background-picture-image_913719.jpg') center/cover no-repeat;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: -1;
        }

        /* 第一页样式 */
        #landing-page {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            position: relative;
        }

        .intro-text {
            max-width: 800px;
            font-size: 1.8rem;
            line-height: 1.6;
            margin-bottom: 60px;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1.2s ease forwards 0.5s;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .scroll-down {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            color: var(--primary-color);
            font-size: 2rem;
            cursor: pointer;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0) translateX(-50%);
            }
            40% {
                transform: translateY(-10px) translateX(-50%);
            }
            60% {
                transform: translateY(-5px) translateX(-50%);
            }
        }

        /* 第二页样式 */
        #resume-page {
            min-height: 100vh;
            padding: 40px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            margin-bottom: 40px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .name-title {
            text-align: left;
        }

        .name {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .title {
            font-size: 1.2rem;
            color: var(--secondary-color);
        }

        .contact-icons {
            display: flex;
            gap: 20px;
        }

        .contact-icons a {
            color: var(--primary-color);
            font-size: 1.5rem;
            transition: var(--transition);
        }

        .contact-icons a:hover {
            color: var(--accent-color);
            transform: translateY(-3px);
        }

        /* 导航 */
        .nav {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }

        .nav a {
            color: var(--secondary-color);
            text-decoration: none;
            font-weight: 500;
            padding: 8px 16px;
            border-radius: 20px;
            transition: var(--transition);
        }

        .nav a:hover, .nav a.active {
            color: var(--primary-color);
            background: rgba(255, 255, 255, 0.1);
        }

        /* 内容布局 */
        .content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 40px;
        }

        @media (max-width: 900px) {
            .content {
                grid-template-columns: 1fr;
            }
        }

        /* 卡片样式 */
        .card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            transition: var(--transition);
            opacity: 0;
            transform: translateY(20px);
        }

        .card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
        }

        .card-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--primary-color);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .card-title i {
            color: var(--accent-color);
        }

        /* 技能样式 */
        .skill {
            margin-bottom: 20px;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
        }

        .skill-bar {
            height: 8px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            overflow: hidden;
        }

        .skill-level {
            height: 100%;
            background: linear-gradient(90deg, var(--accent-color), #8a84ff);
            border-radius: 4px;
            width: 0;
            transition: width 1.5s ease;
        }

        /* 兴趣样式 */
        .interests {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }

        .interest {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            padding: 15px;
            background: var(--card-bg-light);
            border-radius: 10px;
            transition: var(--transition);
            min-width: 100px;
        }

        .interest:hover {
            transform: translateY(-5px);
            background: rgba(108, 99, 255, 0.2);
        }

        .interest i {
            font-size: 1.8rem;
            color: var(--accent-color);
        }

        /* 时间线样式 */
        .timeline {
            position: relative;
            padding-left: 30px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: var(--accent-color);
        }

        .timeline-item {
            position: relative;
            margin-bottom: 30px;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -36px;
            top: 5px;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: var(--accent-color);
            box-shadow: 0 0 0 4px rgba(108, 99, 255, 0.2);
        }

        .timeline-date {
            font-size: 0.9rem;
            color: var(--secondary-color);
            margin-bottom: 5px;
        }

        .timeline-title {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }

        .timeline-subtitle {
            font-size: 1rem;
            color: var(--secondary-color);
            margin-bottom: 10px;
        }

        .timeline-content {
            background: var(--card-bg-light);
            padding: 15px;
            border-radius: 8px;
            margin-top: 10px;
        }

        /* 项目样式 */
        .project {
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .project:last-child {
            border-bottom: none;
        }

        .project-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 15px 0;
        }

        .tech-tag {
            background: rgba(108, 99, 255, 0.2);
            color: var(--accent-color);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
        }

        /* 星光闪烁效果 */
        .twinkling {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .star {
            position: absolute;
            background-color: white;
            border-radius: 50%;
            animation: twinkle 5s infinite ease-in-out;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.2; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>
    <!-- 背景元素 -->
    <div class="stars-bg"></div>
    <div class="overlay"></div>
    <div class="twinkling" id="twinkling"></div>

    <!-- 第一页：引导页 -->
    <section id="landing-page">
        <div class="intro-text">
            <p>我是一名物联网工程专业的毕业生，具备扎实的硬件与软件技术基础。在实习中参与了大棚环境监测系统的开发，熟练运用传感器、嵌入式系统和物联网通信技术。同时，我热爱文学写作，善于将复杂的技术概念转化为清晰易懂的文字。我相信技术能力与写作能力的结合，能够为团队创造独特的价值。</p>
        </div>
        <div class="scroll-down" onclick="scrollToResume()">
            <i class="fas fa-chevron-down"></i>
        </div>
    </section>

    <!-- 第二页：详细简历页 -->
    <section id="resume-page">
        <div class="header">
            <div class="name-title">
                <h1 class="name">吴仲贤</h1>
                <p class="title">物联网工程师</p>
            </div>
            <div class="contact-icons">
                <a href="tel:19194152335"><i class="fas fa-phone"></i></a>
                <a href="mailto:351094580@qq.com"><i class="fas fa-envelope"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin"></i></a>
            </div>
        </div>

        <nav class="nav">
            <a href="#about" class="active">个人简介</a>
            <a href="#education">教育背景</a>
            <a href="#skills">技能栈</a>
            <a href="#experience">工作经历</a>
            <a href="#projects">个人项目</a>
            <a href="#interests">兴趣爱好</a>
        </nav>

        <div class="content">
            <!-- 左侧栏 -->
            <div class="left-column">
                <div id="about" class="card">
                    <h2 class="card-title"><i class="fas fa-user"></i> 个人简介</h2>
                    <p>我是一名物联网工程专业的毕业生，具备扎实的专业技术基础。拥有良好的心态、坚韧的意志和强烈的责任感，吃苦耐劳，勇于面对挑战。在生活中始终秉持着对阅读和写作的热爱，善于将复杂的想法转化为清晰、有逻辑的文字。我坚信，技术能力与写作能力相结合，能够为公司在技术文档、产品说明等方面创造更多价值。</p>
                </div>

                <div id="skills" class="card">
                    <h2 class="card-title"><i class="fas fa-code"></i> 技能栈</h2>
                    <div class="skill">
                        <div class="skill-name">
                            <span>电路分析</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" data-level="85"></div>
                        </div>
                    </div>
                    <div class="skill">
                        <div class="skill-name">
                            <span>嵌入式系统</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" data-level="80"></div>
                        </div>
                    </div>
                    <div class="skill">
                        <div class="skill-name">
                            <span>传感器技术</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" data-level="80"></div>
                        </div>
                    </div>
                    <div class="skill">
                        <div class="skill-name">
                            <span>物联网通信</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" data-level="75"></div>
                        </div>
                    </div>
                    <div class="skill">
                        <div class="skill-name">
                            <span>单片机原理</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" data-level="80"></div>
                        </div>
                    </div>
                    <div class="skill">
                        <div class="skill-name">
                            <span>数据结构</span>
                            <span>70%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" data-level="70"></div>
                        </div>
                    </div>
                    <div class="skill">
                        <div class="skill-name">
                            <span>文学写作</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-level" data-level="90"></div>
                        </div>
                    </div>
                </div>

                <div id="interests" class="card">
                    <h2 class="card-title"><i class="fas fa-heart"></i> 兴趣爱好</h2>
                    <div class="interests">
                        <div class="interest">
                            <i class="fas fa-pen-fancy"></i>
                            <span>文学创作</span>
                        </div>
                        <div class="interest">
                            <i class="fas fa-book"></i>
                            <span>阅读写作</span>
                        </div>
                        <div class="interest">
                            <i class="fas fa-running"></i>
                            <span>长跑运动</span>
                        </div>
                        <div class="interest">
                            <i class="fas fa-users"></i>
                            <span>社会实践</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 右侧栏 -->
            <div class="right-column">
                <div id="education" class="card">
                    <h2 class="card-title"><i class="fas fa-graduation-cap"></i> 教育背景</h2>
                    <div class="timeline">
                        <div class="timeline-item">
                            <div class="timeline-date">2021.09 - 2025.06</div>
                            <h3 class="timeline-title">兰州工业学院</h3>
                            <p class="timeline-subtitle">物联网工程（本科）</p>
                            <div class="timeline-content">
                                <p>主修课程：电路分析、模拟电子技术、数字电子技术与EDA、信号与系统、通信原理、单片机原理与接口技术、数据结构、Linux操作系统、数据库原理及应用、计算机网络、传感器原理及应用、物联网通信技术、嵌入式系统与设计、物联网工程规划与实施、云计算部署与运维。</p>
                            </div>
                        </div>
                    </div>
                </div>

                <div id="experience" class="card">
                    <h2 class="card-title"><i class="fas fa-briefcase"></i> 工作经历</h2>
                    <div class="timeline">
                        <div class="timeline-item">
                            <div class="timeline-date">2024.05 - 2024.05</div>
                            <h3 class="timeline-title">兰州思航智能科技有限公司</h3>
                            <p class="timeline-subtitle">生产实习生</p>
                            <div class="timeline-content">
                                <ul>
                                    <li>参与基于数字温湿度传感器的大棚环境监测系统项目</li>
                                    <li>负责传感器部署、数据采集与传输模块调试</li>
                                    <li>使用Arduino/树莓派进行数据校准与预处理</li>
                                    <li>通过4G/NB-IoT模块实现数据上传与远程监控</li>
                                    <li>开发阈值告警功能，支持手机APP/Web界面查看</li>
                                </ul>
                            </div>
                        </div>
                        <div class="timeline-item">
                            <div class="timeline-date">2023.07 - 2023.08</div>
                            <h3 class="timeline-title">兰州新基德数培有限公司</h3>
                            <p class="timeline-subtitle">招生顾问（兼职）</p>
                            <div class="timeline-content">
                                <ul>
                                    <li>负责成人在线教育的市场拓展、课程咨询与招生转化</li>
                                    <li>通过线上社群运营挖掘潜在学员，提供专业咨询</li>
                                    <li>累计成功招收学员8名，超额完成招生目标</li>
                                    <li>有效提升了沟通说服能力和市场开拓能力</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>

                <div id="projects" class="card">
                    <h2 class="card-title"><i class="fas fa-project-diagram"></i> 校内实践</h2>
                    <div class="project">
                        <h3 class="project-title"><i class="fas fa-pen"></i> 纯文学写作</h3>
                        <p>从2021年10月进入大学以来，一直进行纯文学写作，已经创作小说诗歌随笔累计四十余万字，部分作品曾获得过奖项。</p>
                    </div>
                    <div class="project">
                        <h3 class="project-title"><i class="fas fa-book"></i> 诗歌民刊编辑</h3>
                        <p>2022年12月至2023年1月参与诗歌民刊编辑工作，包括策划内容，线上召开编辑会议，分配工作任务，撰写创刊词，按照时间周期约稿，改稿，将完稿交与编审审阅。与印刷厂商谈印刷事宜，检查样本，督促印刷厂按时按量完成印刷。</p>
                    </div>
                    <div class="project">
                        <h3 class="project-title"><i class="fas fa-hands-helping"></i> 社会实践与志愿服务</h3>
                        <p>参加假期大学生返家乡社会实践活动。在学校512万里长跑中报名志愿者，维持现场秩序。</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        // 滚动到简历页
        function scrollToResume() {
            document.getElementById('resume-page').scrollIntoView({ behavior: 'smooth' });
        }

        // 创建闪烁星星
        function createStars() {
            const twinkling = document.getElementById('twinkling');
            const starCount = 150;
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // 随机位置和大小
                const size = Math.random() * 3;
                const left = Math.random() * 100;
                const top = Math.random() * 100;
                const delay = Math.random() * 5;
                
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                star.style.left = `${left}%`;
                star.style.top = `${top}%`;
                star.style.animationDelay = `${delay}s`;
                
                twinkling.appendChild(star);
            }
        }

        // 滚动动画
        function handleScrollAnimations() {
            const cards = document.querySelectorAll('.card');
            
            cards.forEach(card => {
                const cardTop = card.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (cardTop < windowHeight * 0.9) {
                    card.classList.add('visible');
                }
            });
        }

        // 技能条动画
        function animateSkills() {
            const skillLevels = document.querySelectorAll('.skill-level');
            
            skillLevels.forEach(level => {
                const width = level.getAttribute('data-level') + '%';
                level.style.width = width;
            });
        }

        // 导航高亮
        function highlightNav() {
            const sections = document.querySelectorAll('section, .card');
            const navLinks = document.querySelectorAll('.nav a');
            
            let currentSection = '';
            
            sections.forEach(section => {
                const sectionTop = section.getBoundingClientRect().top;
                if (sectionTop <= 100) {
                    currentSection = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === currentSection) {
                    link.classList.add('active');
                }
            });
        }

        // 初始化
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            animateSkills();
            
            // 初始显示可见卡片
            setTimeout(() => {
                handleScrollAnimations();
            }, 500);
            
            // 滚动事件监听
            window.addEventListener('scroll', function() {
                handleScrollAnimations();
                highlightNav();
            });
        });
    </script>
</body>
</html># 
