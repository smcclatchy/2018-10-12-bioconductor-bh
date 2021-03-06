---
layout: workshop      # DON'T CHANGE THIS.
carpentry: ""
venue: "The Jackson Laboratory"
address: "Breezeway Bioinformatics Training Room, Bldg 1, Room 1540, 600 Main Street, Bar Harbor, Maine"
country: "us"
language: "en"
latlng: "44.365336,-68.196283"
humandate: "Oct 12, 2018"
humantime: "9:00 am - 4:30 pm"
startdate: 2018-10-12
enddate: 2018-10-12    
instructor: ["Sue McClatchy, Asli Uyar, Dan Gatti"]
helper: ["Yuka Takemon, Duy Pham"]
email: ["susan.mcclatchy@jax.org"]
collaborative_notes: https://pad.carpentries.org/2018-10-12-bioconductor-bh
eventbrite: 49899011286
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
This workshop is open to those who have met the prerequisite by taking a 2-day R workshop or otherwise being competent in R.
The workshop is open to those at the Jackson Laboratory and neighboring institutions.


{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use https://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %} 
 SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="https://www.surveymonkey.com/r/8CZHFDF">Pre-workshop Survey</a></p>
<p><a href="https://www.surveymonkey.com/r/8JN5DK9">Post-workshop Survey</a></p>
<hr/>


{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>
{% include sc/schedule.html %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
  SYLLABUS

  Show what topics will be covered.

  1. If your workshop is R rather than Python, remove the comment
     around that section and put a comment around the Python section.
  2. Some workshops will delete SQL.
  3. Please make sure the list of topics is synchronized with what you
     intend to teach.
  4. You may need to move the div's with class="col-md-6" around inside
     the div's with class="row" to balance the multi-column layout.

  This is one of the places where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

1. Find, install, and learn how to use Bioconductor packages
2. Import and manipulate genomic files and Bioconductor data objects
3. Visually assess quality of RNA-seq data
4. Perform basic differential analysis of RNA-seq data
5. Understand how to apply the GenomicRanges infrastructure to real-world problems
6. Gain insight into the design principles of the GenomicRanges infrastructure and how it was meant to be used
7. Learn about various annotation package and public data resources
<p><a href="https://bioconductor.github.io/BiocWorkshops/">Reference...</a></p>

<hr/>

{% comment %}
  SETUP

  Delete irrelevant sections from the setup instructions.  Each
  section is inside a 'div' without any classes to make the beginning
  and end easier to find.

  This is the other place where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

<div id="r"> {% comment %} Start of 'R' section. {% endcomment %}
  <h3>R</h3>

  <p>
    <a href="https://www.r-project.org">R</a> is a programming language
    that is especially powerful for data exploration, visualization, and
    statistical analysis. To interact with R, we use
    <a href="https://www.rstudio.com/">RStudio</a>.
    If you already have R and RStudio installed on your machine,
    <i><b>please upgrade to the latest versions of each</b></i>.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="r-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=q0PjTAylwoU">Video Tutorial</a>
      <p>
        Install R by downloading and running
        <a href="https://cran.r-project.org/bin/windows/base/release.htm">this .exe file</a>
        from <a href="https://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
        Note that if you have separate user and admin accounts, you should run the 
        installers as administrator (right-click on .exe file and select "Run as 
        administrator" instead of double-clicking). Otherwise problems may occur later, 
        for example when installing R packages.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=5-ly3kyxwEg">Video Tutorial</a>
      <p>
        Install R by downloading and running
        <a href="https://cran.r-project.org/bin/macosx/R-latest.pkg">this .pkg file</a>
        from <a href="https://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-linux">Linux</h4>
      <p>
        You can download the binary files for your distribution
        from <a href="https://cran.r-project.org/index.html">CRAN</a>. Or
        you can use your package manager (e.g. for Debian/Ubuntu
        run <code>sudo apt-get install r-base</code> and for Fedora run
        <code>sudo dnf install R</code>).  Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'R' section. {% endcomment %}

<div id="Bioconductor"> {% comment %} Start of 'Bioconductor' section. {% endcomment %}
    <h3>Bioconductor</h3>
    <p>
    <a href="https://www.bioconductor.org/">Bioconductor</a> provides
    tools for the analysis and comprehension of high-throughput
    genomic data. Bioconductor uses the R statistical programming
    language, and is open source and open development.
    The current release of Bioconductor is version 3.7; it works with R version 3.5.0.
    Users of older R and Bioconductor must update their installation to take
    advantage of new features and to access packages that have been added to
    Bioconductor since the last release.
    </p>
  <div class="row">
        <div class="col-md-4">
        <h4 id="packages">Packages</h4>
    <p>
    Packages available in Bioconductor are summarized at https://bioconductor.org/packages.
    The widget on the left summarizes four distinct types of Bioconductor packages:
    1) software, 2) annotation, 3) experiment data, and 4) workflow.
     Like CRAN (R) packages, Bioconductor packages need to be installed only once per R installation,
    and then attached to each session where they are going to be used. Bioconductor packages are installed
    slightly differently from CRAN packages. The first step is to install the <code>BiocManager</code> package from CRAN.
    Open RStudio, then copy and paste the following code into the console:
    </p>
  
  <pre><code>if (!"BiocManager" %in% rownames(installed.packages()))
  install.packages("BiocManager", repos="https://cran.r-project.org")</code></pre>
  The next step is to install the desired Bioconductor packages.
    The syntax to install the packages is
  
  <pre><code>BiocManager::install(c("rtracklayer", "GenomicRanges", "SummarizedExperiment", "DESeq2", "tximportData", "airway", "apeglm", "AnnotationHub", "ReportingTools", "Glimma", "splatter"))</code></pre>
  
  A convenient function in <code>BiocManager</code> is <code>available()</code>, which accepts a regular expression to find matching packages. The following finds all <code>TxDb</code> packages (describing exon, transcript, and gene coordinates).
  
  <pre><code>BiocManager::available("TxDb")</code></pre>
  
  Use the <code>BiocManager::install()</code> function above to install UCSC known genes for human hg38 and mouse mm10.
  
  <pre><code>BiocManager::install(c("TxDb.Hsapiens.UCSC.hg38.knownGene", "TxDb.Mmusculus.UCSC.mm10.knownGene"))</code></pre>
  
  Bioconductor packages tend to depend on one another quite alot,
    so it is important that the correct versions of all packages are installed.
    Validate your installation with
    <pre><code>BiocManager::valid()</code></pre>
    In addition to the Bioconductor packages named above, we'll use some of the
    R packages from <code>tidyverse</code>. Run the following code in the console,
    or install packages from the RStudio Packages tab.
    <pre><code>install.packages("tidyverse")</code></pre>

</div>
    <div class="col-md-4">
    <h4>Project organization</h4>
    <ol>
    <li>Make a new folder in your Desktop called <code>bioconductor</code>.</li>
    <li>Move into this new folder.</li>
    <li>Create  a <code>data</code> folder to hold the data, a <code>scripts</code> folder to house your scripts, and a <code>results</code> folder to hold results.</li>
    </ol>
    Alternatively, you can use the R console to run the following commands for steps 1-3.
    <pre><code>
    setwd("~/Desktop")
    dir.create("./bioconductor")
    setwd("~/Desktop/bioconductor")
    dir.create("./data")
    dir.create("./scripts")
    dir.create("./results")</code></pre>
    </div>
        <div class="col-md-4">
        <h4>Data</h4>
        <p>
        Please download the following large files <b>before the workshop</b>, and place them in your <code>data</code> folder. You can download the files from the URLs below and move the files the same way that you would for downloading and moving any other kind of file.
        <ul>
        <li><a href="https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/CpGislands.Hsapiens.hg38.UCSC.bed">human CPG islands BED file</a> (977 KB)</li>
        <li><a href="https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/CpGislands.Mmusculus.mm10.UCSC.bed">mouse CPG islands BED file</a> (502 KB)</li>
        <li><a href="https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/airway_colData.csv">airway experimental data</a> (941 B)</li>
        <li><a href="https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/airway_counts.csv">airway counts data</a> (1.32 MB)</li>
         </ul>
    </p>
    </div>
</div> {% comment %} End of 'Bioconductor' section. {% endcomment %}
