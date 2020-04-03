<script>
  import Separator from './Separator.svelte';
  import Skill from './Skill.svelte';
  import Accordion from './Accordion.svelte';
  import { 
    UserIcon,
    BriefcaseIcon,
    GlobeIcon,
    ClockIcon,
    ExternalLinkIcon,
    ToolIcon,
    TerminalIcon,
    BookIcon,
    Edit2Icon
  } from 'svelte-feather-icons';
  import Projects from '../info/projects.js';
</script>

<style>
  .app-content {
    background-color: var(--dark-foreground);
    padding: 2rem;
    margin: 0.5rem;
    border-radius: 0.5rem;
    display: flex;
    flex-direction: column;
    min-height: calc(100vh - 2.75rem);
    /* overflow-y: scroll; */
  }

  @media screen and (max-width: 576px) {
    .app-content {
      padding: 1.2rem;
    }
  }

  .content-item:not(:first-child) {
    margin-top: 1.5rem;
  }

  .content-item-header {
    display: flex;
    flex-direction: row;
    align-items: center;
    color: var(--gray-300);
  }

  .content-item-header-text {
    font-size: 1.5rem;
    padding-left: 0.75rem;
  }

  .content-item-body {
    color: var(--gray-400);
  }

  .content-item-body a {
    color: inherit;
    /* text-decoration: none; */
    font-weight: bold;
    font-size: 1.25rem;
  }

  .job-experience-container {
    display: flex;
    flex-direction: column;
  }

  .job-detail-row {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .job-detail-row span {
    font-style: italic;
    font-size: 0.9rem;
  }

  .job-detail-description {
    margin-top: 0.25rem;
  }

  .skill-set {
    line-height: 2rem;
  }
</style>

<div class='app-content'>
  <div class='content-item'>
    <div class='content-item-header'>
      <UserIcon size='24' />
      <span class='content-item-header-text'>ABOUT</span>
    </div>
    <Separator />
    <div class='content-item-body'>
      <p>Hey there!</p>
      <p>I did my graduation from IEM, Kolkata with a major in computer science carrying 8.72 DGPA. After college, I joined FusionCharts as javascript
      developer where I worked on the primary product of the company, FusionCharts Suite XT. While most of work was focussed on using VanillaJS, I also got
      the opportunity to delve into other frameworks and libraries like React, Svelte, Angular.</p>
      <p>I have worked extensively on the performance optimizations of FusionCharts, which later proved to be a competitive advantage over other
      charting libraries. I have one article as well, please check the articles section of this page.</p>
      <p>Starting last year, I started mentoring junior developers by guiding them on how to navigate through challenging problems. I have also taken 
      part in hiring process and helped hire 4 key members of the team.</p>
      <p>I am always up for a chat. Feel free to reach out.</p>
    </div>
  </div>
  <div class='content-item'>
    <div class='content-item-header'>
      <BriefcaseIcon size='24' />
      <span class='content-item-header-text'>WORK EXPERIENCE</span>
    </div>
    <Separator />
    <div class='content-item-body'>
      <div class='job-experience-container'>
        <div class='job-detail-row'>
          <a href='https://www.fusioncharts.com/' target="_blank" rel="noopener noreferrer">FusionCharts <ExternalLinkIcon size='15' /></a>
          <div style='display: flex; align-items: center;'>
            <GlobeIcon size='12' /> &nbsp;
            <span>Kolkata, India</span>
          </div>
        </div>
        <div class='job-detail-row'>
          <div href=''>Senior Software Engineer</div>
          <div style='display: flex; align-items: center;'>
            <ClockIcon size='12' /> &nbsp;
            <span>April, 2019 - Present</span>
          </div>
        </div>
        <div class='job-detail-description'>
          <ul>
            <li>Provide guidance to a team of junior developers, helping them with research and understanding of new feature requirements. Take part in planning of release scopes and sprints.</li>
            <li>Planning and development of discontinuous time axis to accomodate stock data information in FusionTime.</li>
            <li>Developed FaberJS, a platform agnostic javascript implementation of CSS grid. FaberJS can be used to implement CSS grids in SVG.</li>
            <li>Created a wrapper of FusionCharts for Svelte to help capture the market of Svelte developers as no other charting libraries provides a wrapper.</li>
            <li>Created new visualizations: Sankey diagram and Chord diagram.</li>
            <li>Take part in hiring process. Helped in hiring 4 key members of the team.</li>
          </ul>
        </div> 
        <div class='job-detail-row'>
          <div href=''>Software Engineer</div>
          <div style='display: flex; align-items: center;'>
            <ClockIcon size='12' /> &nbsp;
            <span>July, 2017 - March, 2019</span>
          </div>
        </div>
        <div class='job-detail-description'>
          <ul>
            <li>Revamped FusionCharts codebase from ES3 to ES6. Increased modularity and extensibility of codebase to make rapid development and quick iterations of new features easier.</li>
            <li>Worked extensively on performance optimizations of FusionCharts. Rewrote caching module of the rendering engine. Improved performance of S​martlabel​ by ~75%.</li>
            <li>Planning and development of FusionTime. Developed core functionalities of time scale from scratch which is used by various time-dependent FusionTime components.</li>
            <li>Created internal dashboards using React, Redux.</li>
            <li>Maintenance of front-end wrappers(React, Angular, Svelte).</li>
          </ul>
        </div> 
      </div>
    </div>
  </div>
  <div class='content-item'>
    <div class='content-item-header'>
      <ToolIcon size='24' />
      <span class='content-item-header-text'>TECHNICAL SKILLS</span>
    </div>
    <Separator />
    <div class='content-item-body skill-set'>
      <Skill>JavaScript</Skill>
      <Skill>HTML</Skill>
      <Skill>CSS</Skill>
      <Skill>React</Skill>
      <Skill>Redux</Skill>
      <Skill>Svelte</Skill>
      <Skill>BootStrap</Skill>
      <Skill>SCSS</Skill>
      <Skill>Webpack</Skill>
      <Skill>Jest</Skill>
      <Skill>Jasmine</Skill>
      <Skill>Gulp</Skill>
    </div>
  </div>
  <div class='content-item'>
    <div class='content-item-header'>
      <TerminalIcon size='24' />
      <span class='content-item-header-text'>PROJECTS</span>
    </div>
    <Separator />
    <div class='content-item-body'>
      <Accordion items={Projects}/>
    </div>
  </div>
  <div class='content-item'>
    <div class='content-item-header'>
      <BookIcon size='24' />
      <span class='content-item-header-text'>EDUCATION</span>
    </div>
    <Separator />
    <div class='content-item-body'>
    </div>
  </div>
  <div class='content-item'>
    <div class='content-item-header'>
      <Edit2Icon size='24' />
      <span class='content-item-header-text'>PUBLICATIONS</span>
    </div>
    <Separator />
    <div class='content-item-body'>
    </div>
  </div>
</div>