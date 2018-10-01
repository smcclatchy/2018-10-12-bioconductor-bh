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
instructor: ["Asli Uyar, Dan Gatti"]
helper: ["Yuka Takemon, Duy Pham, Sue McClatchy"]   
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
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

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
{% if site.carpentry == "swc" %} 
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "dc" %}
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "lc" %}
<p><a href="{{ site.lc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.lc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}

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

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

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
    slightly differently from CRAN packages. The first step is to install the BiocManager package from CRAN.
    Open RStudio, then copy and paste the following code into the console:
    </p>
  
  <pre><code class="keyword">if (!"BiocManager" %in% rownames(installed.packages()))
  install.packages("BiocManager", repos="https://cran.r-project.org")</code></pre>

     ~~~
    if (!"BiocManager" %in% rownames(installed.packages()))
    install.packages("BiocManager", repos="https://cran.r-project.org")
    ~~~
    {: .r}
    
    The next step is to install the desired Bioconductor packages.
    The syntax to install the rtracklayer, GenomicRanges, SummarizedExperiment,
    and DESeq2 packages is
    
    ~~~
    BiocManager::install(c("rtracklayer", "GenomicRanges", "SummarizedExperiment", "DESeq2"))
    ~~~
    {: .r}
    
    A convenient function in BiocManager is available(), which accepts a regular expression to find matching packages. The following finds all ‘TxDb’ packages (describing exon, transcript, and gene coordinates).
    
    ~~~
    BiocManager::available("TxDb")
    ~~~
    {: .r}
    
    Use the BiocManager::install() function above to install UCSC known genes for human hg38
    and mouse mm10.
    
    ~~~
    BiocManager::install(c("TxDb.Hsapiens.UCSC.hg38.knownGene", "TxDb.Mmusculus.UCSC.mm10.knownGene"))
    ~~~
    {: .r}
    
    Bioconductor packages tend to depend on one another quite alot,
    so it is important that the correct versions of all packages are installed.
    Validate your installation with
    
    ~~~
    BiocManager::valid()
    ~~~
    {: .r}
</div>
    <div class="col-md-4">
    <h4>Project organization</h4>
    <p>
    1. Make a new folder in your Desktop called `bioconductor`. Move into this new folder.
    2. Create  a `data` folder to hold the data, a `scripts` folder to house your scripts, and a `results` folder to hold results.
    Alternatively, you can use the R console to run the following commands for steps 1 and 2.
    ~~~
    setwd("~/Desktop")
    dir.create("./bioconductor")
    setwd("~/Desktop/bioconductor")
    dir.create("./data")
    dir.create("./scripts")
    dir.create("./results")
    ~~~
    {: .r}
    </p>
    </div>
        <div class="col-md-4">
        <h4>Data</h4>
        <p>
        Please download the following large files **before the workshop**, and place them in your `data` folder. You can download the files from the URLs below and move the files the same way that you would for downloading and moving any other kind of data.
        - [human CPG islands BED file](https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/CpGislands.Hsapiens.hg38.UCSC.bed) (977 KB)
        - [mouse CPG islands BED file](https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/CpGislands.Mmusculus.mm10.UCSC.bed) (502 KB)
        - [airway experimental data](https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/airway_colData.csv) (941 B)
        - [airway counts data](https://raw.githubusercontent.com/smcclatchy/2018-10-12-bioconductor-bh/gh-pages/data/100_Morgan_RBiocForAll/airway_counts.csv) (1.32 MB)
    </p>
    </div>

</div> {% comment %} End of 'Bioconductor' section. {% endcomment %}
