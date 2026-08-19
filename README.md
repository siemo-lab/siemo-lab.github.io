# siemo-lab.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SIEMO Lab - Social Interaction and Emotion Lab</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --navy: #1F3A4C;
            --teal: #5FA8AE;
            --light-teal: #8FC3C8;
            --forest: #2D5F5C;
            --white: #FFFFFF;
            --light-gray: #F8F8F8;
            --text-dark: #333333;
            --text-light: #666666;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            background-color: var(--white);
        }

        /* Header & Navigation */
        header {
            background-color: var(--navy);
            color: var(--white);
            padding: 1.5rem 2rem;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(31, 58, 76, 0.15);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 600;
            letter-spacing: -0.5px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-size: 0.95rem;
            transition: opacity 0.2s;
            border-bottom: 2px solid transparent;
        }

        .nav-links a:hover {
            opacity: 0.8;
            border-bottom-color: var(--light-teal);
        }

        .nav-links a.active {
            border-bottom-color: var(--light-teal);
        }

        /* Main Container */
        main {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Page Sections */
        .page {
            display: none;
            min-height: calc(100vh - 200px);
            padding: 3rem 0;
        }

        .page.active {
            display: block;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 2rem 0;
            border-bottom: 2px solid var(--light-teal);
            margin-bottom: 3rem;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            color: var(--navy);
        }

        .hero p {
            font-size: 1.1rem;
            color: var(--text-light);
        }

        /* Home Page */
        .home-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: start;
        }

        .photo-section {
            text-align: center;
        }

        .group-photo {
            width: 100%;
            max-width: 400px;
            height: auto;
            border-radius: 12px;
            object-fit: cover;
            margin-bottom: 1.5rem;
        }

        .bio-section h2 {
            font-size: 1.5rem;
            color: var(--navy);
            margin-bottom: 1rem;
        }

        .bio-section p {
            margin-bottom: 1rem;
            color: var(--text-dark);
            line-height: 1.8;
        }

        .recruiting-box {
            background-color: var(--light-teal);
            padding: 1.5rem;
            border-radius: 8px;
            margin: 1.5rem 0;
            color: var(--white);
        }

        .recruiting-box a {
            color: var(--white);
            font-weight: 600;
            text-decoration: underline;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 2rem;
            font-size: 1.5rem;
        }

        .social-links a {
            color: var(--teal);
            text-decoration: none;
            transition: color 0.2s;
        }

        .social-links a:hover {
            color: var(--forest);
        }

        /* Members Page */
        .members-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .member-card {
            background-color: var(--light-gray);
            padding: 1.5rem;
            border-radius: 8px;
            text-align: center;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .member-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 16px rgba(95, 168, 174, 0.15);
        }

        .member-photo {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            margin: 0 auto 1rem;
            border: 3px solid var(--teal);
        }

        .member-card h3 {
            font-size: 1.1rem;
            color: var(--navy);
            margin-bottom: 0.3rem;
        }

        .member-card .title {
            font-size: 0.9rem;
            color: var(--text-light);
            margin-bottom: 0.5rem;
        }

        .member-card .email {
            font-size: 0.85rem;
            color: var(--teal);
            text-decoration: none;
            word-break: break-all;
        }

        .member-card .cv-link {
            display: inline-block;
            margin-top: 0.8rem;
            padding: 0.5rem 1rem;
            background-color: var(--teal);
            color: var(--white);
            text-decoration: none;
            border-radius: 4px;
            font-size: 0.85rem;
            transition: background-color 0.2s;
        }

        .member-card .cv-link:hover {
            background-color: var(--forest);
        }

        .section-divider {
            border-top: 2px solid var(--light-teal);
            margin: 2rem 0;
            padding-top: 2rem;
        }

        .collaborators-section h3 {
            font-size: 1.3rem;
            color: var(--navy);
            margin-bottom: 1rem;
        }

        /* Research Page */
        .research-intro {
            background-color: var(--light-gray);
            padding: 2rem;
            border-radius: 8px;
            margin-bottom: 2rem;
        }

        .research-intro h2 {
            color: var(--navy);
            margin-bottom: 1rem;
        }

        .research-questions {
            display: grid;
            gap: 1.5rem;
        }

        .question-box {
            background-color: var(--light-teal);
            color: var(--white);
            padding: 1.5rem;
            border-radius: 8px;
            border-left: 5px solid var(--forest);
        }

        .question-box strong {
            display: block;
            margin-bottom: 0.5rem;
            font-size: 1.05rem;
        }

        /* Publications Page */
        .publications-intro {
            background-color: var(--light-gray);
            padding: 1.5rem;
            border-radius: 8px;
            margin-bottom: 2rem;
        }

        .publication-item {
            border: 1px solid #e0e0e0;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            border-radius: 8px;
            background-color: var(--white);
        }

        .publication-item h3 {
            color: var(--navy);
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        .publication-item .status {
            display: inline-block;
            padding: 0.3rem 0.7rem;
            background-color: var(--light-teal);
            color: var(--white);
            font-size: 0.75rem;
            border-radius: 4px;
            margin: 0.5rem 0;
        }

        .publication-item .authors {
            color: var(--text-light);
            font-size: 0.95rem;
            margin: 0.5rem 0;
        }

        .publication-item .links {
            margin-top: 0.8rem;
        }

        .publication-item a {
            color: var(--teal);
            text-decoration: none;
            margin-right: 1rem;
            font-weight: 500;
        }

        .publication-item a:hover {
            text-decoration: underline;
        }

        /* News Page */
        .news-feed {
            display: grid;
            gap: 2rem;
        }

        .news-item {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 1.5rem;
            background-color: var(--light-gray);
            padding: 1.5rem;
            border-radius: 8px;
            border-left: 4px solid var(--teal);
        }

        .news-item.text-only {
            grid-template-columns: 1fr;
        }

        .news-image {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-radius: 6px;
        }

        .news-content h3 {
            color: var(--navy);
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        .news-date {
            color: var(--text-light);
            font-size: 0.85rem;
            margin-bottom: 0.8rem;
        }

        .news-content p {
            color: var(--text-dark);
            line-height: 1.6;
        }

        /* Join Us Page */
        .position-card {
            background-color: var(--light-gray);
            padding: 2rem;
            border-radius: 8px;
            margin-bottom: 2rem;
            border-left: 5px solid var(--teal);
        }

        .position-card h3 {
            color: var(--navy);
            margin-bottom: 1rem;
        }

        .position-card ul {
            margin-left: 1.5rem;
            margin-bottom: 1rem;
        }

        .position-card li {
            margin-bottom: 0.5rem;
        }

        .apply-button {
            display: inline-block;
            padding: 0.8rem 1.5rem;
            background-color: var(--teal);
            color: var(--white);
            text-decoration: none;
            border-radius: 4px;
            font-weight: 600;
            transition: background-color 0.2s;
        }

        .apply-button:hover {
            background-color: var(--forest);
        }

        .policy-section {
            background-color: var(--light-gray);
            padding: 2rem;
            border-radius: 8px;
            margin-top: 2rem;
        }

        .policy-section h3 {
            color: var(--navy);
            margin-bottom: 1rem;
        }

        /* Values Page */
        .values-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .value-card {
            background: linear-gradient(135deg, var(--light-teal) 0%, var(--teal) 100%);
            color: var(--white);
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(95, 168, 174, 0.2);
        }

        .value-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
        }

        /* Footer */
        footer {
            background-color: var(--navy);
            color: var(--white);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 1rem;
            font-size: 1.3rem;
        }

        .footer-links a {
            color: var(--white);
            text-decoration: none;
            transition: color 0.2s;
        }

        .footer-links a:hover {
            color: var(--light-teal);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                gap: 1rem;
                font-size: 0.85rem;
            }

            .hero h1 {
                font-size: 1.8rem;
            }

            .home-content {
                grid-template-columns: 1fr;
            }

            .news-item {
                grid-template-columns: 1fr;
            }

            .members-grid {
                grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            }
        }

        @media (max-width: 600px) {
            .nav-links {
                flex-wrap: wrap;
                gap: 0.8rem;
            }

            .logo {
                font-size: 1.3rem;
            }

            header {
                padding: 1rem;
            }

            main {
                padding: 0 1rem;
            }

            .page {
                padding: 1.5rem 0;
            }

            .hero h1 {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">SIEMO Lab</div>
            <ul class="nav-links">
                <li><a href="#" onclick="showPage('home')" class="nav-link active">Home</a></li>
                <li><a href="#" onclick="showPage('members')" class="nav-link">Members</a></li>
                <li><a href="#" onclick="showPage('research')" class="nav-link">Research</a></li>
                <li><a href="#" onclick="showPage('publications')" class="nav-link">Publications</a></li>
                <li><a href="#" onclick="showPage('news')" class="nav-link">News</a></li>
                <li><a href="#" onclick="showPage('join')" class="nav-link">Join Us</a></li>
                <li><a href="#" onclick="showPage('values')" class="nav-link">Values</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- HOME PAGE -->
        <div id="home" class="page active">
            <div class="hero">
                <h1>Social Interaction and Emotion Lab</h1>
                <p>Understanding how social connections shape emotion and well-being</p>
            </div>

            <div class="home-content">
                <div class="photo-section">
                    <img src="group-photo-url.jpg" alt="SIEMO Lab Group Photo" class="group-photo">
                </div>

                <div class="bio-section">
                    <h2>Welcome to SIEMO</h2>
                    <p>As social creatures, our relationships with other people have tremendous downstream impacts on health and well-being. This is in part because social interactions dramatically shape how we think and feel, influencing how we process and experience emotions through life's challenges.</p>

                    <p>Our research systematically unpacks the effects of social support on emotion and well-being across various modalities and contexts, targeting a process called "social emotion regulation." Through this work, we aim to promote emotional intelligence in how we understand ourselves, each other, and our connections with one another.</p>

                    <div class="recruiting-box">
                        <strong>We're Recruiting!</strong>
                        <p style="margin-top: 0.8rem; margin-bottom: 0;">We're looking for passionate researchers to join our team. Learn more about current opportunities on our <a href="#" onclick="showPage('join'); return false;">Join Us</a> page.</p>
                    </div>

                    <div class="social-links">
                        <a href="https://linkedin.com" title="LinkedIn">in</a>
                        <a href="https://bsky.app" title="Bluesky">☁️</a>
                    </div>
                </div>
            </div>
        </div>

        <!-- MEMBERS PAGE -->
        <div id="members" class="page">
            <div class="hero">
                <h1>Lab Members</h1>
                <p>Meet the researchers behind SIEMO</p>
            </div>

            <div class="members-grid">
                <div class="member-card">
                    <img src="razia-photo.jpg" alt="Razia Sahi" class="member-photo">
                    <h3>Razia Sahi</h3>
                    <div class="title">Principal Investigator</div>
                    <a href="mailto:razia.sahi@rutgers.edu" class="email">razia.sahi@rutgers.edu</a>
                    <a href="cv-razia.pdf" class="cv-link">CV</a>
                </div>

                <div class="member-card">
                    <img src="member1-photo.jpg" alt="Graduate Student" class="member-photo">
                    <h3>Graduate Student</h3>
                    <div class="title">PhD Candidate</div>
                    <a href="mailto:student@rutgers.edu" class="email">student@rutgers.edu</a>
                </div>

                <div class="member-card">
                    <img src="member2-photo.jpg" alt="Postdoctoral Researcher" class="member-photo">
                    <h3>Postdoctoral Researcher</h3>
                    <div class="title">Postdoc</div>
                    <a href="mailto:postdoc@rutgers.edu" class="email">postdoc@rutgers.edu</a>
                </div>
            </div>

            <div class="section-divider"></div>

            <div class="collaborators-section">
                <h3>Friends of the Lab & Collaborators</h3>
                <div class="members-grid">
                    <div class="member-card">
                        <h3>Collaborator Name</h3>
                        <div class="title">Affiliation</div>
                        <a href="mailto:collaborator@example.edu" class="email">collaborator@example.edu</a>
                    </div>
                </div>
            </div>
        </div>

        <!-- RESEARCH PAGE -->
        <div id="research" class="page">
            <div class="hero">
                <h1>Research Directions</h1>
                <p>Current questions guiding our work</p>
            </div>

            <div class="research-intro">
                <h2>Our Approach</h2>
                <p>Our research uses a combination of behavioral experiments, naturalistic data, and multi-modal methods to study how people regulate each other's emotions across contexts such as close relationships, peers, and psychotherapy. This work operates at the intersection of social cognition and affective science to illustrate how we navigate emotions together. We currently have three major lines of research.</p>
            </div>

            <div class="research-questions">
                <div class="question-box">
                    <strong>How do our interactions with others help change our perspectives of emotional experiences?</strong>
                    <p>Changing how we think about emotional experiences can change how we feel about those experiences—a paradigmatic emotion regulation strategy called cognitive reappraisal. But it can be difficult to understand our own emotions, let alone change how we think about them. How do our interactions with others help change our perspectives of emotional experiences?</p>
                </div>

                <div class="question-box">
                    <strong>What role does comfort from others play in emotional processing?</strong>
                    <p>Offering someone new perspectives of negative events can be an effective way to regulate emotions, but challenging someone's understanding of their personal experiences can also lead to feelings of invalidation and create resistance to support. What role does comfort from others—in the form of both verbal and nonverbal support—play in emotional processing?</p>
                </div>

                <div class="question-box">
                    <strong>How do subtle interactive cues facilitate emotion regulation in conversations?</strong>
                    <p>There are lots of different things we can say to help regulate others' emotions. But it's not always just what we say. Sometimes, it's how we say it that makes a difference. How do subtle interactive cues (such as linguistic, acoustic) facilitate emotion regulation in conversations?</p>
                </div>
            </div>
        </div>

        <!-- PUBLICATIONS PAGE -->
        <div id="publications" class="page">
            <div class="hero">
                <h1>Publications</h1>
                <p>Peer-reviewed research and preprints</p>
            </div>

            <div class="publications-intro">
                <p>Below you'll find links to publications and pre-prints, including data and analytic code repositories and relevant blog posts or press articles that communicate this work for a broader audience.</p>
            </div>

            <div class="publication-item">
                <h3>Sharing is believing: Saying or writing reframes of emotional experiences boosts cognitive emotion regulation</h3>
                <span class="status">Under Review</span>
                <div class="authors">Razia S. Sahi | Angela Challman | Erik Nook</div>
                <div class="links">
                    <a href="#">Pre-print</a>
                    <a href="#">Data & Code</a>
                </div>
            </div>

            <div class="publication-item">
                <h3>Examining social emotion regulation in Spanish-English bilinguals</h3>
                <span class="status">Under Review</span>
                <div class="authors">Tiffany Cao | Razia S. Sahi | Chantal A. Valdivia-Moreno | Erik Nook</div>
                <div class="links">
                    <a href="#">Pre-print</a>
                </div>
            </div>

            <div class="publication-item">
                <h3>Large natural emotion vocabularies are linked with better mental health in psychotherapeutic conversations</h3>
                <span class="status">Under Review</span>
                <div class="authors">Razia S. Sahi | James Gross | Tal Yarkoni</div>
                <div class="links">
                    <a href="#">Pre-print</a>
                    <a href="#">Data & Code</a>
                </div>
            </div>
        </div>

        <!-- NEWS PAGE -->
        <div id="news" class="page">
            <div class="hero">
                <h1>Lab News</h1>
                <p>Updates and announcements from SIEMO</p>
            </div>

            <div class="news-feed">
                <div class="news-item">
                    <img src="news1-image.jpg" alt="Lab seminar" class="news-image">
                    <div class="news-content">
                        <h3>Lab Seminar on Emotional Intelligence</h3>
                        <div class="news-date">August 15, 2026</div>
                        <p>The lab gathered to discuss recent findings on how emotion vocabularies relate to mental health outcomes in therapy sessions. An engaging discussion followed about implications for clinical practice.</p>
                    </div>
                </div>

                <div class="news-item text-only">
                    <div class="news-content">
                        <h3>New Lab Member Joins SIEMO</h3>
                        <div class="news-date">August 1, 2026</div>
                        <p>Please welcome our newest graduate student to the lab! They bring expertise in computational linguistics and are excited to work on projects examining language and emotion regulation.</p>
                    </div>
                </div>

                <div class="news-item">
                    <img src="news2-image.jpg" alt="Lab event" class="news-image">
                    <div class="news-content">
                        <h3>Grant Funding Awarded</h3>
                        <div class="news-date">July 20, 2026</div>
                        <p>Congratulations to the lab on receiving funding for a new project examining social emotion regulation in peer relationships. The three-year study will expand our understanding of how friends support each other's emotional well-being.</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- JOIN US PAGE -->
        <div id="join" class="page">
            <div class="hero">
                <h1>Join SIEMO</h1>
                <p>Opportunities to collaborate with our research team</p>
            </div>

            <div class="position-card">
                <h3>Undergraduate Research Assistants</h3>
                <p>We welcome motivated undergraduates to join our lab as research assistants. You'll gain hands-on experience in behavioral research, data collection, and analysis while contributing to studies examining emotion and social interaction.</p>
                <strong>Qualifications:</strong>
                <ul>
                    <li>Strong interest in psychology, emotion, or social science research</li>
                    <li>Ability to commit 8-10 hours per week</li>
                    <li>Attention to detail and reliability</li>
                </ul>
                <a href="mailto:razia.sahi@rutgers.edu?subject=Undergraduate%20RA%20Position" class="apply-button">Inquire About Position</a>
            </div>

            <div class="position-card">
                <h3>Postbaccalaureate Researchers</h3>
                <p>For recent graduates seeking research experience before graduate school, postbac positions offer deeper engagement with ongoing projects. Postbacs contribute to data collection, analysis, and manuscript preparation.</p>
                <strong>Qualifications:</strong>
                <ul>
                    <li>Bachelor's degree in psychology or related field</li>
                    <li>Experience with or interest in learning statistics and coding</li>
                    <li>Ability to commit to a 1-2 year position</li>
                </ul>
                <a href="mailto:razia.sahi@rutgers.edu?subject=Postbac%20Position" class="apply-button">Inquire About Position</a>
            </div>

            <div class="position-card">
                <h3>Graduate Students</h3>
                <p>We recruit doctoral students through the Rutgers Psychology PhD program. Our lab welcomes students interested in emotion, social cognition, clinical science, or computational methods applied to behavioral data.</p>
                <strong>Qualifications:</strong>
                <ul>
                    <li>Admission to Rutgers Psychology PhD Program</li>
                    <li>Research interests aligned with social emotion regulation</li>
                    <li>Strong academic foundation in statistics and research methods</li>
                </ul>
                <p style="margin-top: 1rem;"><strong>Application window:</strong> Fall admission cycle (typically December deadline)</p>
            </div>

            <div class="policy-section">
                <h3>Our Commitment to Candidates</h3>
                <p>We believe in transparent and respectful recruitment. When you reach out to inquire about joining the lab, you can expect:</p>
                <ul style="margin-left: 1.5rem; margin-top: 1rem;">
                    <li>A prompt response within one week</li>
                    <li>Clear information about current opportunities and timeline</li>
                    <li>An honest discussion about lab culture and expectations</li>
                    <li>For graduate students, guidance on the application process and timeline</li>
                </ul>
                <p style="margin-top: 1.5rem;">We welcome questions at any stage—don't hesitate to reach out!</p>
            </div>
        </div>

        <!-- VALUES PAGE -->
        <div id="values" class="page">
            <div class="hero">
                <h1>Lab Values</h1>
                <p>Principles guiding our research and community</p>
            </div>

            <div class="values-grid">
                <div class="value-card">
                    <h3>Rigorous Science</h3>
                    <p>We are committed to conducting careful, thoughtful research that advances our understanding of human emotion and social connection. This means valuing replication, transparency, and continuous improvement of our methods.</p>
                </div>

                <div class="value-card">
                    <h3>Intellectual Generosity</h3>
                    <p>We believe in sharing ideas openly, supporting colleagues, and building on the work of others. Our research is strengthened by collaboration, critical feedback, and the diverse perspectives of our team members.</p>
                </div>

                <div class="value-card">
                    <h3>Emotional Insight</h3>
                    <p>Understanding human emotion requires attending to both the science and the lived experience. We value curiosity about emotional life, empathy, and the wisdom that comes from attending closely to how people experience the world.</p>
                </div>

                <div class="value-card">
                    <h3>Equity and Inclusion</h3>
                    <p>We strive to build a lab community where all researchers feel valued and supported. We are committed to advancing research that benefits diverse populations and to fostering an inclusive environment for our team.</p>
                </div>

                <div class="value-card">
                    <h3>Work-Life Integration</h3>
                    <p>Research is important work, and so is your life outside the lab. We value sustainable practices, mental health, and the diverse roles and responsibilities our team members hold.</p>
                </div>

                <div class="value-card">
                    <h3>Community Impact</h3>
                    <p>We are motivated by research that ultimately benefits people. Whether through clinical applications, public communication, or direct service, we consider how our work can contribute positively to individuals and communities.</p>
                </div>
            </div>
        </div>
    </main>

    <footer>
        <div class="footer-content">
            <p>Social Interaction and Emotion Lab (SIEMO) | Rutgers University–Newark</p>
            <p style="margin-top: 0.5rem; font-size: 0.9rem;">Department of Psychology</p>
            <div class="footer-links">
                <a href="mailto:razia.sahi@rutgers.edu">✉️</a>
                <a href="https://linkedin.com">in</a>
                <a href="https://bsky.app">☁️</a>
            </div>
        </div>
    </footer>

    <script>
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });

            // Remove active from all nav links
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });

            // Show selected page
            document.getElementById(pageId).classList.add('active');

            // Add active to clicked nav link
            event.target.classList.add('active');

            // Scroll to top
            window.scrollTo(0, 0);
        }

        // Prevent default link behavior
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const pageId = this.getAttribute('href').substring(1);
                showPage(pageId);
            });
        });
    </script>
</body>
</html>
