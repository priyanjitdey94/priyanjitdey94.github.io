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
  }

  .job-detail-description {
    margin-top: 1.5rem;
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
      Richard hails from Tulsa. He has earned degrees from the University of Oklahoma and Stanford. (Go Sooners and Cardinals!) Before starting Pied Piper, he worked for Hooli as a part time software developer. While his work focuses on applied information theory, mostly optimizing lossless compression schema of both the length-limited and adaptive variants, his non-work interests range widely, everything from quantum computing to chaos theory. He could tell you about it, but THAT would NOT be a “length-limited” conversation!
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
          <div>
            <GlobeIcon size='12' />
            <span>Kolkata, India</span>
          </div>
        </div>
        <div class='job-detail-row'>
          <div href=''>Software Engineer</div>
          <div>
            <ClockIcon size='12' />
            <span>July, 2017 - Present</span>
          </div>
        </div>
        <div class='job-detail-description'>
          Pied Piper is a multi-platform technology based on a proprietary universal compression algorithm that has consistently fielded high Weisman Scores™ that are not merely competitive, but approach the theoretical limit of lossless compression.
          <ul>
            <li>Provide guidance to a team of junior developers, helping them with research and understanding of new feature requirements. Take part in planning of release scopes and sprints.</li>
            <li>Revamped FusionCharts codebase from ES3 to ES6. Increased modularity and extensibility of codebase to make rapid development and quick iterations of new features easier.</li>
            <li>Worked extensively on performance optimizations of FusionCharts. Rewrote caching module of RedRaphael, rendering engine. Improved performance of S​martlabel​ by ~75%.</li>
            <li>Planning and development of FusionTime. Developed core functionalities of time scale from scratch which is used by various time-dependent FusionTime components.</li>
            <li>Created internal dashboards using React, Redux.</li>
            <li>Created new visualizations: Sankey diagram and Chord diagram.</li>
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
      <Skill>TypeScript</Skill>
      <Skill>ESNext</Skill>
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