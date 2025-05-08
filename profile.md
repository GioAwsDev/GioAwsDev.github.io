---
title: Profile
layout: page
description: AWS-certified cloud professional with expertise in healthcare process optimization, automation, and cloud solutions
keywords: AWS, Cloud Computing, DevOps, Healthcare IT, Automation
last_modified_at: 2024-05-08
---
<div class="profile-image-container">
    ![Profile Image]({% if site.external-image %}{{ site.picture }}{% else %}{{ site.url }}/{{ site.picture }}{% endif %})
</div>

<section class="professional-summary">
    <h2>Professional Summary</h2>
    <div class="summary-content">
        <p>My name is Giovannie, and I'm an AWS-certified cloud professional with proven success optimizing healthcare processes and solving high-priority technical issues. I've improved claims efficiency by 15% at Humana through automation and data-driven solutions.</p>
        <p>Key achievements:</p>
        <ul>
            <li>Boosted claims processing efficiency by 15% by designing and implementing XML macro scripts to automate manual steps in Humana’s claims adjudication workflow.</li>
            <li>Optimized claims tools using Excel and VBA by incorporating advanced logic and Visual Basic macros, increasing speed and accuracy.</li>
            <li>Won AWS National Jam - 2024 (US TA) by leading a team to solve real-world cloud challenges under time constraints, showcasing hands-on AWS expertise and problem-solving skills.</li>
        </ul>
    </div>
</section>

<section class="skills">
    <h2>Skills</h2>
    <ul class="skill-list">
        <li>
            <h3>Cloud & Infrastructure</h3>
            <ul>
                <li>AWS Core Services (EC2, S3, RDS, Lambda)</li>
                <li>Infrastructure as Code (Terraform, CloudFormation)</li>
                <li>CI/CD (Jenkins, GitHub Actions)</li>
                <li>Docker & Kubernetes</li>
            </ul>
        </li>
        <li>
            <h3>Development</h3>
            <ul>
                <li>Python</li>
                <li>HTML/CSS/JavaScript</li>
                <li>Bash Scripting</li>
            </ul>
        </li>
        <li>
            <h3>Frameworks & Tools</h3>
            <ul>
                <li>React</li>
                <li>Django</li>
                <li>Git & GitHub</li>
            </ul>
        </li>
        <li>
            <h3>Data & AI</h3>
            <ul>
                <li>AI/ML (Amazon Bedrock, SageMaker)</li>
                <li>MySQL</li>
            </ul>
        </li>
        <li>
            <h3>Technical Support & Reliability</h3>
            <ul>
                <li>Tier 3 Triage</li>
                <li>Incident Response</li>
                <li>Root Cause Analysis</li>
                <li>Splunk</li>
            </ul>
        </li>
    </ul>
</section>

<section class="certifications">
    <h2>Certifications</h2>
    <div class="certs-container">
        <a href="https://www.credly.com/users/giovannie-encarnacion" class="credly-link">View on Credly</a>
        <div class="cert-grid">
            <img alt="AWS Cloud Application Developer Graduate" width="100px" src="https://images.credly.com/images/b709da03-24b0-4777-8393-f76c9131b893/blob"/>
            <img alt="Red Hat Certified System Administrator" width="100px" src="https://images.credly.com/images/572de0ba-2c59-4816-a59d-b0e1687e45ee/image.png" />
            <img alt="CompTIA Security+" width="100px" src="https://images.credly.com/size/340x340/images/80d8a06a-c384-42bf-ad36-db81bce5adce/blob" />
            <img alt="AWS Certified Developer Associate" width="100px" src="https://images.credly.com/size/340x340/images/b9feab85-1a43-4f6c-99a5-631b88d5461b/image.png" />
            <img alt="AWS Certified SysOps Admin Associate" width="100px" src="https://images.credly.com/size/340x340/images/f0d3fbb9-bfa7-4017-9989-7bde8eaf42b1/image.png" />
            <img alt="AWS Certified Solutions Architect Associate" width="100px" src="https://images.credly.com/size/340x340/images/0e284c3f-5164-4b21-8660-0d84737941bc/image.png" />
            <img alt="AWS Cloud Practitioner" width="100px" src="https://images.credly.com/size/340x340/images/00634f82-b07f-4bbd-a6bb-53de397fc3a6/image.png" />
        </div>
    </div>
</section>

<style>
.cert-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 20px;
    margin-top: 20px;
}

.credly-link {
    display: inline-block;
    margin-bottom: 20px;
    padding: 10px 20px;
    background-color: #0077b5;
    color: white;
    text-decoration: none;
    border-radius: 5px;
}

.credly-link:hover {
    background-color: #005582;
    transform: translateY(-2px);
    transition: all 0.3s ease;
}

.cert-grid img {
    transition: transform 0.3s ease;
    cursor: pointer;
}

.cert-grid img:hover {
    transform: scale(1.1);
}

.skill-list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    padding: 0;
    list-style: none;
}

.skill-list > li {
    background: #f8f9fa;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.skill-list > li > ul {
    margin-top: 1rem;
    padding-left: 1.5rem;
}

.skill-list h3 {
    margin: 0 0 1rem 0;
    color: #2c3e50;
}
</style>

.profile-image-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px 0; /* Optional: Add spacing around the image */
}

.profile-image-container img {
    border-radius: 50%; /* Optional: Make the image circular */
    max-width: 150px; /* Optional: Adjust the size of the image */
    height: auto;
}

