---
title: Join Us
layout: default
permalink: /
---

{% assign now = 'now' | date: '%s' %}
{% assign sortedinfosessions = site.data.info_sessions | future_info_sessions %}

{% assign open = site.pages | open_positions | sort: 'title' %}
{% assign upcoming = site.pages | upcoming_positions | sort: 'title' %}

<section class="usa-hero padding-y-6">
  <div class="grid-container">
      <h1 class="usa-hero__heading--alt font-heading-l font-family-sans margin-top-0 tablet:margin-bottom-0">
        Find your opportunity to make a difference.
      </h1>
      <h2 class="usa-hero__heading margin-top-2 font-heading-2xl line-height-heading-4">
        Help us <span class="usa-hero__heading--highlight">design and deliver a digital government</span> with and for the American public.
      </h2>
  </div>
</section>
<section class="usa-section">
  <div class="grid-container">
    <div class="grid-row grid-gap">
      <div class="desktop:grid-col-12 margin-bottom-3">
        <p class="usa-intro margin-top-0">
          We’re looking for candidates who are passionate about helping agencies build, buy, and share technology to better serve the public. Our team focuses on all aspects of digital government including account management, software development, product management, procurement, design, content strategy, cloud migration, outreach, and operations.
        </p>
        <div class="usa-prose">
          <p>
          The Technology Transformation Services' (TTS) mission is to design and deliver a digital government with and for the American public. TTS is part of the General Services Administration (GSA).
          </p>
          <p>
          We are accepting applications for the positions listed below. We also post upcoming positions. <a href="{% link pages/newsletter.md %}">Join our mailing list</a> to be notified when we post new jobs.
          </p>
        </div>
      </div>
    </div>
    <div class="grid-row grid-gap">
      <div class="desktop:grid-col-8 usa-prose position-list">
        <h2 id="open-positions">Open positions</h2>
        {% if open.size > 0 %}
        <p>We are hiring and will be sharing upcoming jobs and open positions as they are available.</p>
        <ul>
        {% for job in open %}
          {% unless job.path contains 'template' %}
          {% unless job.path contains 'performance-profiles' %}
          {% assign info_sessions = job | future_info_sessions_for_job %}
          <li class="{% if info_sessions.size > 0 %}with-info-sessions{% endif %}">
            {{ infosessions.size }}<a href="{{ site.baseurl }}{{ job.url }}">{{ job.title }}</a>
            (Open now through {{ job.closes | human_friendly }}{% if job["max applications"] > 0 %}, or when {{ job["max applications"] }} applications have been received{% endif %})
            {%- include info_sessions.html job=job %}
          </li>
          {% endunless %}
          {% endunless %}
        {% endfor %}
        </ul>
        {% else %}
          <p>
            No open positions at this time. Sign up for
            <a href="{% link pages/newsletter.md %}">job alerts</a>!
          </p>
        {% endif %}

        <h2> Upcoming positions</h2>
        {% if upcoming.size > 0 %}
        <ul>
        {% for job in upcoming %}
          {% unless job.path contains 'template' %}
          {% unless job.path contains 'performance-profiles' %}
          {% assign info_sessions = job | future_info_sessions_for_job %}
          <li class="{% if info_sessions.size > 0 %}with-info-sessions{% endif %}">
            <h3><a href="{{ site.baseurl }}{{ job.url }}">{{ job.title }}</a></h3>
            {%- include info_sessions.html job=job %}
          </li>
          {% endunless %}
          {% endunless %}
        {% endfor %}
        </ul>
        {% else %}
          <p>
            No upcoming positions at this time. Sign up for
            <a href="{% link pages/newsletter.md %}">job alerts</a>!
          </p>
        {% endif %}
        <h2> Other GSA Opportunities </h2>
       <p> Check out <a href="https://www.gsa.gov/about-us/careers">careers at GSA</a> and more <a href="https://www.usajobs.gov/Search/Results?j=2210&d=GS&p=1">Information Technology opportunities.</a></p>

        <h2>Application process</h2>
        <p>
        We have an amazing recruitment team who will usher you from application to interview to onboarding with TTS.
        You’ll have guidance every step of the way! Learn more about our <a href="{% link pages/hiring-process.md %}">hiring process</a>.
        </p>
        <p>
          If you have any questions about the process or positions, please contact
          our Talent Team at <a href="mailto:joinTTS@gsa.gov">joinTTS@gsa.gov</a>.
        </p>
      </div>
      <div class="desktop:grid-col-4 margin-top-4 desktop:margin-top-0">
        <div class="usa-summary-box">
          <div class="usa-summary-box__body">
            <h3 class="usa-summary-box__heading">
              Find Out More
            </h3>
            <div class="usa-summary-box__text">
              <p>
                Join us at one of our monthly online information sessions. Come
                learn more about working at TTS, available positions, and our
                application process. Register for a session below.
              </p>
              <ul>
                {% for session in sortedinfosessions %}
                    <li><p><a target="_blank" href="{{ session.link }}">{{ session.date | human_friendly }}</a><br/>{{ session.time }}</p></li>
                {% endfor %}
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>

  </div>
  </section>
  <section class="usa-section usa-section--dark margin-top-6">
    <div class="grid-container">
      <div class="grid-row grid-gap">
        <div class="desktop:grid-col-8 usa-prose">
          <h3>About Technology Transformation Services</h3>
          <p>
            Technology Transformation Services (TTS) applies modern methodologies and technologies to improve the public’s experience with government. We help agencies make their services more accessible, efficient, and effective with modern applications, platforms, processes, personnel, and software solutions.
          </p>
          <p>
            TTS is comprised of four business units and front office, operations, and acquisition teams. Learn more about the <a href="{% link pages/tts-offices.md %}">offices that make up TTS</a>.
          </p>
        </div>
        <div class="desktop:grid-col-4 usa-prose">
          <h4>Our offices</h4>
          <ul>
            <li><a href="{% link pages/tts-offices.md %}/#centers-of-excellence"><strong>Centers of Excellence</strong></a></li>
            <li><a href="{% link pages/tts-offices.md %}/#18f"><strong>18F</strong></a></li>
            <li><a href="{% link pages/tts-offices.md %}/#office-of-solutions"><strong>Office of Solutions</strong></a></li>
            <li><a href="{% link pages/tts-offices.md %}/#presidential-innovation-fellows"><strong>Presidential Innovation Fellows</strong></a></li>
            <li><a href="{% link pages/tts-offices.md %}/#us-digital-corps"><strong>US Digital Corps</strong></a></li>
            <li><a href="{% link pages/tts-offices.md %}/#tts-front-office"><strong>TTS Front Office</strong></a></li>
            <li><a href="{% link pages/tts-offices.md %}/#office-of-operations"><strong>Office of Operations</strong></a></li>
            <li><a href="{% link pages/tts-offices.md %}/#office-of-acquisition"><strong>Office of Acquisition</strong></a></li>
          </ul>
        </div>
      </div>
  </div>
</section>
