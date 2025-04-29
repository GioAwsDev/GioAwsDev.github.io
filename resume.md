---
title: Resume
layout: page
---

<div class="resume-container">
    <iframe id="resumeFrame" src="{{ site.url }}/assets/resume.pdf" width="100%" height="1100px" style="border: none;">
        This browser does not support PDFs. Please download the PDF to view it: 
        <a href="{{ site.url }}/assets/resume.pdf">Download PDF</a>
    </iframe>
</div>

<div class="resume-download">
    <a href="{{ site.url }}/assets/resume.pdf" class="btn" download>
        Download Resume
    </a>
</div>

<style>
    .resume-container {
        width: 100%;
        margin: 20px 0;
        position: relative;
        padding-bottom: 10px;
    }
    .resume-container iframe {
        min-height: 1100px;
        max-width: 100%;
        margin: 0 auto;
        display: block;
    }
    @media screen and (max-width: 768px) {
        .resume-container iframe {
            height: 800px;
        }
    }
    .resume-download {
        text-align: center;
        margin: 20px 0;
    }
    .btn {
        display: inline-block;
        padding: 10px 20px;
        background-color: #0366d6;
        color: white;
        text-decoration: none;
        border-radius: 4px;
    }
    .btn:hover {
        background-color: #024ea4;
    }
</style>

<script>
    document.getElementById('resumeFrame').onload = function() {
        this.style.height = this.contentWindow.document.documentElement.scrollHeight + 'px';
    };
</script>
