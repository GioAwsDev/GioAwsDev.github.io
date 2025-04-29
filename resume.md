---
title: Resume
layout: page
---

<div class="resume-container">
    <object
        data="{{ site.url }}/assets/resume.pdf"
        type="application/pdf"
        width="100%"
        height="1200px"
        id="resume-object">
        <iframe
            src="https://docs.google.com/viewer?url={{ site.url | url_encode }}/assets/resume.pdf&embedded=true"
            width="100%"
            height="1200px"
            style="border: none;">
            <p>Your browser does not support PDFs.
            <a href="{{ site.url }}/assets/resume.pdf">Download the PDF</a> to view it.</p>
        </iframe>
    </object>
</div>

<div class="resume-download">
    <a href="{{ site.url }}/assets/resume.pdf" class="btn" download>
        Download Resume
    </a>
</div>

<style>
    .resume-container {
        width: 100%;
        margin: 20px auto;
        max-width: 1000px; /* Prevents the resume from getting too wide on large screens */
    }
    
    object, iframe {
        display: block;
        border: none;
        background: white;
        box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    
    /* Responsive adjustments */
    @media screen and (max-width: 768px) {
        .resume-container object,
        .resume-container iframe {
            height: 900px;
        }
    }
    
    .resume-download {
        text-align: center;
        margin: 20px 0;
    }
    
    .btn {
        display: inline-block;
        padding: 12px 24px;
        background-color: #0366d6;
        color: white;
        text-decoration: none;
        border-radius: 4px;
        font-weight: 600;
        transition: background-color 0.2s ease;
    }
    
    .btn:hover {
        background-color: #024ea4;
        text-decoration: none;
    }
</style>

<script>
window.onload = function() {
    // Adjust height based on content
    function adjustHeight() {
        var obj = document.getElementById('resume-object');
        if (obj) {
            // Get viewport height
            var viewportHeight = Math.max(document.documentElement.clientHeight, window.innerHeight || 0);
            // Set minimum height
            obj.style.height = Math.max(1200, viewportHeight * 0.85) + 'px';
        }
    }
    
    // Adjust on load and resize
    adjustHeight();
    window.addEventListener('resize', adjustHeight);
}
</script>
