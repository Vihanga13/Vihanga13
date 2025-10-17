<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vihanga Nilusha - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Courier New', 'Monaco', 'Menlo', monospace;
            background: #0d1117;
            color: #c9d1d9;
            line-height: 1.6;
            background-image: 
                linear-gradient(90deg, transparent 24%, rgba(0, 212, 255, 0.05) 25%, rgba(0, 212, 255, 0.05) 26%, transparent 27%, transparent 74%, rgba(0, 212, 255, 0.05) 75%, rgba(0, 212, 255, 0.05) 76%, transparent 77%, transparent),
                linear-gradient(0deg, transparent 24%, rgba(0, 212, 255, 0.05) 25%, rgba(0, 212, 255, 0.05) 26%, transparent 27%, transparent 74%, rgba(0, 212, 255, 0.05) 75%, rgba(0, 212, 255, 0.05) 76%, transparent 77%, transparent);
            background-size: 50px 50px;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Terminal-like styling */
        .terminal {
            max-width: 100%;
            margin: 0;
            background: #0d1117;
            position: relative;
        }

        .terminal-header {
            background: #161b22;
            border-bottom: 1px solid #30363d;
            padding: 12px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
            animation: slideDown 0.6s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .terminal-buttons {
            display: flex;
            gap: 8px;
        }

        .terminal-btn {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.2s;
        }

        .btn-red { background: #ff5f56; }
        .btn-yellow { background: #ffbd2e; }
        .btn-green { background: #27c93f; }

        .terminal-btn:hover {
            transform: scale(1.2);
        }

        .terminal-title {
            color: #8b949e;
            font-size: 13px;
            flex: 1;
            text-align: center;
        }

        .terminal-content {
            padding: 20px 30px;
            animation: fadeIn 0.8s ease-out 0.3s both;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #0d1117;
        }

        ::-webkit-scrollbar-thumb {
            background: #30363d;
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #484f58;
        }

        /* Content Styling */
        .line {
            display: flex;
            align-items: center;
            padding: 2px 0;
            min-height: 24px;
            animation: typeWriter 0.05s ease-out forwards;
        }

        @keyframes typeWriter {
            from {
                opacity: 0;
                transform: translateX(-10px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .line-number {
            display: inline-block;
            width: 40px;
            text-align: right;
            color: #6e7681;
            margin-right: 20px;
            user-select: none;
            font-size: 12px;
        }

        .line-content {
            flex: 1;
            font-size: 13px;
            letter-spacing: 0.5px;
        }

        /* Syntax Highlighting */
        .keyword {
            color: #ff7b72;
        }

        .string {
            color: #a5d6ff;
        }

        .function {
            color: #d2a8ff;
        }

        .property {
            color: #79c0ff;
        }

        .comment {
            color: #8b949e;
            font-style: italic;
        }

        .number {
            color: #79c0ff;
        }

        .operator {
            color: #ff7b72;
        }

        .name {
            color: #c9d1d9;
        }

        .emoji {
            font-style: normal;
            margin: 0 2px;
        }

        .section-divider {
            color: #30363d;
            margin: 10px 0;
        }

        h2 {
            color: #58a6ff;
            margin-top: 20px;
            margin-bottom: 10px;
            font-size: 16px;
            font-weight: bold;
            animation: slideInLeft 0.4s ease-out backwards;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .indent {
            margin-left: 20px;
        }

        .indent-2 {
            margin-left: 40px;
        }

        .indent-3 {
            margin-left: 60px;
        }

        .highlight {
            background: rgba(88, 166, 255, 0.15);
            border-left: 2px solid #58a6ff;
            padding-left: 10px;
        }

        .table-row {
            display: grid;
            grid-template-columns: 2fr 3fr 2fr 1fr;
            gap: 20px;
            padding: 8px 0;
            border-bottom: 1px solid #21262d;
        }

        .table-header {
            color: #58a6ff;
            font-weight: bold;
            border-bottom: 2px solid #30363d;
            padding-bottom: 10px;
        }

        .status-badge {
            display: inline-block;
            padding: 2px 8px;
            border-radius: 4px;
            font-size: 11px;
            font-weight: bold;
        }

        .status-active {
            background: rgba(3, 102, 214, 0.3);
            color: #58a6ff;
        }

        .status-progress {
            background: rgba(183, 119, 31, 0.3);
            color: #d29922;
        }

        .status-planning {
            background: rgba(98, 61, 143, 0.3);
            color: #bc8cdb;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .terminal-content {
                padding: 15px 20px;
            }

            .line-number {
                width: 30px;
                margin-right: 15px;
                font-size: 11px;
            }

            .line-content {
                font-size: 12px;
            }

            .table-row {
                grid-template-columns: 1fr;
                gap: 5px;
            }
        }
    </style>
</head>
<body>
    <div class="terminal">
        <div class="terminal-header">
            <div class="terminal-buttons">
                <div class="terminal-btn btn-red"></div>
                <div class="terminal-btn btn-yellow"></div>
                <div class="terminal-btn btn-green"></div>
            </div>
            <div class="terminal-title">vihanga@github ~ README.md</div>
            <div style="width: 60px;"></div>
        </div>

        <div class="terminal-content">
            <div class="line" style="animation-delay: 0.05s">
                <span class="line-number">1</span>
                <span class="line-content"><span class="comment"># 👋 Hi, I'm Vihanga Nilusha</span></span>
            </div>

            <div class="line" style="animation-delay: 0.1s">
                <span class="line-number">2</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 0.15s">
                <span class="line-number">3</span>
                <span class="line-content"><span class="string">**Full Stack Developer | UI/UX Designer | Mobile Developer**</span></span>
            </div>

            <div class="line" style="animation-delay: 0.2s">
                <span class="line-number">4</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 0.25s">
                <span class="line-number">5</span>
                <span class="line-content">Computer Science student at <span class="string">University of Plymouth</span>, passionate about</span>
            </div>

            <div class="line" style="animation-delay: 0.3s">
                <span class="line-number">6</span>
                <span class="line-content">building beautiful and functional digital experiences.</span>
            </div>

            <div class="line" style="animation-delay: 0.35s">
                <span class="line-number">7</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 0.4s">
                <span class="line-number">8</span>
                <span class="line-content"><span class="keyword">const</span> <span class="property">vihanga</span> = {</span>
            </div>

            <div class="line indent" style="animation-delay: 0.45s">
                <span class="line-number">9</span>
                <span class="line-content"><span class="property">name</span>: <span class="string">"Vihanga Nilusha"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 0.5s">
                <span class="line-number">10</span>
                <span class="line-content"><span class="property">education</span>: <span class="string">"University of Plymouth"</span> 🎓,</span>
            </div>

            <div class="line indent" style="animation-delay: 0.55s">
                <span class="line-number">11</span>
                <span class="line-content"><span class="property">email</span>: <span class="string">"vihaax23@gmail.com"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 0.6s">
                <span class="line-number">12</span>
                <span class="line-content"><span class="property">specializations</span>: [</span>
            </div>

            <div class="line indent-2" style="animation-delay: 0.65s">
                <span class="line-number">13</span>
                <span class="line-content"><span class="string">"Full Stack Development"</span> 🚀,</span>
            </div>

            <div class="line indent-2" style="animation-delay: 0.7s">
                <span class="line-number">14</span>
                <span class="line-content"><span class="string">"UI/UX Design"</span> 🎨,</span>
            </div>

            <div class="line indent-2" style="animation-delay: 0.75s">
                <span class="line-number">15</span>
                <span class="line-content"><span class="string">"Mobile App Development"</span> 📱</span>
            </div>

            <div class="line indent" style="animation-delay: 0.8s">
                <span class="line-number">16</span>
                <span class="line-content">],</span>
            </div>

            <div class="line indent" style="animation-delay: 0.85s">
                <span class="line-number">17</span>
                <span class="line-content"><span class="property">currentlyLearning</span>: [<span class="string">"React Native"</span>, <span class="string">"Flutter"</span>, <span class="string">"Advanced React"</span>, <span class="string">"Node.js"</span>],</span>
            </div>

            <div class="line indent" style="animation-delay: 0.9s">
                <span class="line-number">18</span>
                <span class="line-content"><span class="property">interests</span>: [<span class="string">"Web Development"</span>, <span class="string">"Mobile Development"</span>, <span class="string">"UI/UX"</span>, <span class="string">"Open Source"</span>],</span>
            </div>

            <div class="line indent" style="animation-delay: 0.95s">
                <span class="line-number">19</span>
                <span class="line-content"><span class="property">motto</span>: <span class="string">"Go Beyond The Boundaries"</span> 🚀</span>
            </div>

            <div class="line" style="animation-delay: 1s">
                <span class="line-number">20</span>
                <span class="line-content">};</span>
            </div>

            <div class="line section-divider" style="animation-delay: 1.05s">
                <span class="line-number">21</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 1.1s">
                <span class="line-number">22</span>
                <span class="line-content"><span class="comment">// 💻 Tech Stack</span></span>
            </div>

            <div class="line" style="animation-delay: 1.15s">
                <span class="line-number">23</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 1.2s">
                <span class="line-number">24</span>
                <span class="line-content"><span class="keyword">const</span> <span class="property">techStack</span> = {</span>
            </div>

            <div class="line indent" style="animation-delay: 1.25s">
                <span class="line-number">25</span>
                <span class="line-content"><span class="property">frontend</span>: [<span class="string">"HTML5"</span>, <span class="string">"CSS3"</span>, <span class="string">"JavaScript"</span>, <span class="string">"TypeScript"</span>, <span class="string">"React"</span>, <span class="string">"Next.js"</span>, <span class="string">"TailwindCSS"</span>, <span class="string">"Figma"</span>, <span class="string">"Adobe XD"</span>],</span>
            </div>

            <div class="line indent" style="animation-delay: 1.3s">
                <span class="line-number">26</span>
                <span class="line-content"><span class="property">backend</span>: [<span class="string">"Node.js"</span>, <span class="string">"Express.js"</span>, <span class="string">"Python"</span>, <span class="string">"PHP"</span>, <span class="string">"Java"</span>],</span>
            </div>

            <div class="line indent" style="animation-delay: 1.35s">
                <span class="line-number">27</span>
                <span class="line-content"><span class="property">databases</span>: [<span class="string">"MongoDB"</span>, <span class="string">"MySQL"</span>, <span class="string">"PostgreSQL"</span>, <span class="string">"Firebase"</span>],</span>
            </div>

            <div class="line indent" style="animation-delay: 1.4s">
                <span class="line-number">28</span>
                <span class="line-content"><span class="property">mobile</span>: [<span class="string">"React Native"</span>, <span class="string">"Flutter"</span>, <span class="string">"Dart"</span>, <span class="string">"Expo"</span>],</span>
            </div>

            <div class="line indent" style="animation-delay: 1.45s">
                <span class="line-number">29</span>
                <span class="line-content"><span class="property">tools</span>: [<span class="string">"Git"</span>, <span class="string">"Docker"</span>, <span class="string">"Vercel"</span>, <span class="string">"Netlify"</span>, <span class="string">"VS Code"</span>, <span class="string">"Postman"</span>]</span>
            </div>

            <div class="line" style="animation-delay: 1.5s">
                <span class="line-number">30</span>
                <span class="line-content">};</span>
            </div>

            <div class="line section-divider" style="animation-delay: 1.55s">
                <span class="line-number">31</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 1.6s">
                <span class="line-number">32</span>
                <span class="line-content"><span class="comment">// 🎯 Featured Projects</span></span>
            </div>

            <div class="line" style="animation-delay: 1.65s">
                <span class="line-number">33</span>
                <span class="line-content"></span>
            </div>

            <div class="line table-header" style="animation-delay: 1.7s">
                <span class="line-number">34</span>
                <span class="line-content">
                    <span style="display: grid; grid-template-columns: 2fr 3fr 2fr 1fr; gap: 20px; width: 100%;">
                        <span>PROJECT</span>
                        <span>DESCRIPTION</span>
                        <span>TECH STACK</span>
                        <span>STATUS</span>
                    </span>
                </span>
            </div>

            <div class="line table-row" style="animation-delay: 1.75s">
                <span class="line-number">35</span>
                <span class="line-content" style="display: grid; grid-template-columns: 2fr 3fr 2fr 1fr; gap: 20px; width: 100%;">
                    <span><span class="emoji">🛒</span> E-Commerce</span>
                    <span>Complete shopping platform with admin dashboard</span>
                    <span>React, Node.js, MongoDB</span>
                    <span><span class="status-badge status-progress">In Progress</span></span>
                </span>
            </div>

            <div class="line table-row" style="animation-delay: 1.8s">
                <span class="line-number">36</span>
                <span class="line-content" style="display: grid; grid-template-columns: 2fr 3fr 2fr 1fr; gap: 20px; width: 100%;">
                    <span><span class="emoji">✅</span> Task Manager</span>
                    <span>Cross-platform productivity app with sync</span>
                    <span>React Native, Firebase</span>
                    <span><span class="status-badge status-active">Active</span></span>
                </span>
            </div>

            <div class="line table-row" style="animation-delay: 1.85s">
                <span class="line-number">37</span>
                <span class="line-content" style="display: grid; grid-template-columns: 2fr 3fr 2fr 1fr; gap: 20px; width: 100%;">
                    <span><span class="emoji">🍽️</span> Restaurant App</span>
                    <span>Full-featured dining platform with ordering</span>
                    <span>Flutter, Node.js, MySQL</span>
                    <span><span class="status-badge status-active">Active</span></span>
                </span>
            </div>

            <div class="line table-row" style="animation-delay: 1.9s">
                <span class="line-number">38</span>
                <span class="line-content" style="display: grid; grid-template-columns: 2fr 3fr 2fr 1fr; gap: 20px; width: 100%;">
                    <span><span class="emoji">🎨</span> UI/UX Portfolio</span>
                    <span>Design showcase with interactive prototypes</span>
                    <span>Figma, Adobe XD, Framer</span>
                    <span><span class="status-badge status-planning">Planning</span></span>
                </span>
            </div>

            <div class="line section-divider" style="animation-delay: 1.95s">
                <span class="line-number">39</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 2s">
                <span class="line-number">40</span>
                <span class="line-content"><span class="comment">// 🌟 Core Skills</span></span>
            </div>

            <div class="line" style="animation-delay: 2.05s">
                <span class="line-number">41</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 2.1s">
                <span class="line-number">42</span>
                <span class="line-content"><span class="keyword">const</span> <span class="property">skills</span> = {</span>
            </div>

            <div class="line indent" style="animation-delay: 2.15s">
                <span class="line-number">43</span>
                <span class="line-content"><span class="string">"Web Development"</span>: <span class="string">"Building responsive, scalable applications"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 2.2s">
                <span class="line-number">44</span>
                <span class="line-content"><span class="string">"Mobile Development"</span>: <span class="string">"Cross-platform experiences for iOS & Android"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 2.25s">
                <span class="line-number">45</span>
                <span class="line-content"><span class="string">"UI/UX Design"</span>: <span class="string">"Intuitive interfaces that balance aesthetics"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 2.3s">
                <span class="line-number">46</span>
                <span class="line-content"><span class="string">"Full-Stack Solutions"</span>: <span class="string">"End-to-end development with scalability"</span></span>
            </div>

            <div class="line" style="animation-delay: 2.35s">
                <span class="line-number">47</span>
                <span class="line-content">};</span>
            </div>

            <div class="line section-divider" style="animation-delay: 2.4s">
                <span class="line-number">48</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 2.45s">
                <span class="line-number">49</span>
                <span class="line-content"><span class="comment">// 🤝 Let's Connect</span></span>
            </div>

            <div class="line" style="animation-delay: 2.5s">
                <span class="line-number">50</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 2.55s">
                <span class="line-number">51</span>
                <span class="line-content"><span class="keyword">const</span> <span class="property">connect</span> = {</span>
            </div>

            <div class="line indent" style="animation-delay: 2.6s">
                <span class="line-number">52</span>
                <span class="line-content"><span class="property">linkedin</span>: <span class="string">"https://linkedin.com/in/vihanga-nilusha"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 2.65s">
                <span class="line-number">53</span>
                <span class="line-content"><span class="property">github</span>: <span class="string">"https://github.com/Vihanga13"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 2.7s">
                <span class="line-number">54</span>
                <span class="line-content"><span class="property">email</span>: <span class="string">"vihaax23@gmail.com"</span>,</span>
            </div>

            <div class="line indent" style="animation-delay: 2.75s">
                <span class="line-number">55</span>
                <span class="line-content"><span class="property">discord</span>: <span class="string">"https://discord.gg/yourdiscord"</span></span>
            </div>

            <div class="line" style="animation-delay: 2.8s">
                <span class="line-number">56</span>
                <span class="line-content">};</span>
            </div>

            <div class="line section-divider" style="animation-delay: 2.85s">
                <span class="line-number">57</span>
                <span class="line-content"></span>
            </div>

            <div class="line" style="animation-delay: 2.9s">
                <span class="line-number">58</span>
                <span class="line-content"><span class="comment">// ⭐ Don't forget to star my repositories!</span></span>
            </div>

            <div class="line" style="animation-delay: 2.95s">
                <span class="line-number">59</span>
                <span class="line-content"><span class="comment">// Made with ❤️ and ☕ by Vihanga Nilusha</span></span>
            </div>

            <div class="line" style="animation-delay: 3s">
                <span class="line-number">60</span>
                <span class="line-content"><span class="comment">// Go Beyond The Boundaries 🚀</span></span>
            </div>

        </div>
    </div>
</body>
</html>
