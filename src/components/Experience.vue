<template>
  <div id="experienceBody">
    <h4 id="experience">Experience</h4>
    <div id="legend" class="container">
        <div class="row">
          <div class="col colorLead">
            Leadership <i class="fas fa-users"></i>
          </div>
          <div class="col colorCloud">
            Cloud <i class="fas fa-cloud"></i>
          </div>
          <div class="col colorDev">
            Development <i class="fas fa-code-branch"></i>
          </div>
        </div>
    </div>
    <div v-for="company in companies" id="companyContainer">  
      <div class="container">
        <div class="row">
          <div id="companyContainer" class="col">
            <img :src="company.logo" />
            <div>{{ company.name }}</div>
          </div>
          <div id="titleContainer" class="col">
            <h5>{{ company.title }}</h5>
            <h5>{{ company.time }}</h5>
          </div>
        </div>
      </div>
      <br>
      <div v-if="company.contractingPosition" id="contractPositionTitles">
        Positions held on client site: 
        <span v-for="(experience, index) in company.experiences">
          <span id="contractPositionTitleList"> {{ experience.title }}</span><span v-if="index != company.experiences.length-1">,</span>
        </span>
      </div>
      <div class="container">
        <div class="row">
          <div v-for="experience in company.experiences" class="col experienceContainers">
            <h5 class="experienceListTitle">{{ experience.title }} <span class="experienceDuration">{{ experience.duration }}</span></h5>
            <ul class="list-group list-group-flush">
              <li v-for="note in experience.notes" class="list-group-item"> 
                <span class="colorLead" v-if="['Leads', 'Collaborates'].includes(note.substring(0, note.indexOf(' ')))">{{ note.substring(0, note.indexOf(' ')) }}</span>
                <span class="colorCloud" v-else-if="['Architects', 'Automates', 'Advises', 'Documents'].includes(note.substring(0, note.indexOf(' ')))">{{ note.substring(0, note.indexOf(' ')) }}</span>
                <span class="colorDev" v-else-if="['Builds', 'Maintains', 'Prototypes'].includes(note.substring(0, note.indexOf(' ')))">{{ note.substring(0, note.indexOf(' ')) }}</span>
                <span v-else>{{ note.substring(0, note.indexOf(' ')) }}</span>
                {{ note.substring(note.indexOf(" "), note.length)}}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Experience',
  data() {
    return {
      companies: [
        {
          name: 'Evans & Chambers Technology LLC.',
          logo: 'https://s3.amazonaws.com/resume-host-images/ec.png',
          title: 'Software Engineer',
          time: '2013 - Present',
          contractingPosition: true,
          experiences: [
            {
              title: 'Developer Team Lead',
              duration: '(2016 - Present)',
              notes: [
                'Leads a small agile development team building high visibility applications that are critical to the customer\'s security posture',
                'Collaborates with other developers using GitHub and code reviews',
                'Architects multi-network application designs and creates presentation material for security panel review boards',
                'Automates production blue-green deployments using a combination of Jenkins, Cloudformation, ELB, AutoScaling, and the AWS Node SDK',
                'Automates production log monitoring by bootstrapping the CloudWatch Logs Agent, creating CloudWatch Metrics, and sending SNS notifications',
                'Automates continuous dev & test deployments with a combination of Git, Jenkins, S3, cron, and custom linux bash shell scripts (There are restrictions barring us from using CodeDeploy)',
                'Automates dev virtual workstation provisioning using cloudformation with a custom Windows AMI and a batch bootstrap script (There are restrictions barring us from using WorkStations',
                'Builds Java Spring Boot applications from scratch, incorporating RESTful API best practices, Spring Security, embedded Tomcat, and JPA for data access',
                'Builds authentication using Public Key Infrastructure (PKI) integration for cert based single sign-on',
                'Builds PL/SQL scripts for data migration, cleanup, view creation, and reports',
                'Builds test endpoints for end-to-end testing and add hooks for Swagger integration',
                'Builds new pages and modifies an existing Angular 1 application',
                'Maintains a legacy Java EE application and it\'s native SQL data access layer'
              ]
            },
            {
              title: 'Cloud Architect',
              duration: '(2015 - 2016)',
              notes: [
                'Advises customer leadership on how to use AWS Consolidated Billing to save costs and maximize Reserved Instance benefits',
                'Architects log aggregation solution across all customer servers in all cloud accounts, forwarding them to an in-house log analysis system',
                'Architects infrastructure design diagrams and price estimation sheets to be packed as a proposal to Project Managers',
                'Documents infrastructure security mechanisms as part of a package sent to customer security staff for gaining project approval',
                'Automates Java infrastructure using the AWS Ruby SDK',
                'Automates Tomcat and httpd server bootstrapping using Ruby and linux bash shell scripts',
                'Prototypes Elasticache Logstash Kibana (ELK) stack for central log aggregation, analysis, and visualization'
              ]
            },
            {
              title: 'Full Stack Developer',
              duration: '(2013 - 2015)',
              notes: [
                'Builds and designs Ext JS web applications from scratch',
                'Builds Java Grails applications from scratch, incorporating Spring Security and GORM for data access',
                'Builds new REST APIs into several existing Spring Applications serving data to multiple front end applications',
                'Prototypes Ember.js for a team held web framework "Bake Off" to choose a new framework to replace Ext JS'
              ]
            }
          ]
        },
        {
          name: 'Hughes Network Systems LLC.',
          logo: 'https://s3.amazonaws.com/resume-host-images/hughes.svg',
          title: 'Software Engineer',
          time: '2012 - 2013',
          contractingPosition: false,
          experiences: [
            {
              title: 'Software Engineer I ',
              duration: '(2012 - 2013)',
              notes: [
                'Builds global network device mapping interface for commercial satellite internet customers from scratch using OpenSteetMap',
                'Builds new functionality into an existing Grails applications being maintained by multiple teams',
                'Builds SQL scripts for database schema versioning and rollback capabilities'
              ]
            }
          ]
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#experienceBody {
  background-color: #555555;
  color: #ffffff;
  margin-top: 7rem;
  padding-bottom: 3rem;
}
#experience {
  padding-top: 2rem;
}
img {
  height: 50px;
}
#titleContainer {
  text-align: right;
  margin-top: 2rem;
}
#companyContainer {
  text-align: left;
  margin-top: 2rem;
}
#contractPositionTitles {
  text-align: center;
}
#contractPositionTitleList {
  color: #dddddd;
}
.list-group-item {
    background-color: #555555;
    text-align: left;
    border: none;
    padding-top: 4px;
    padding-bottom: 4px;
    font-size: 0.9rem;
    color: #dddddd;
}
.experienceListTitle {
  text-align: left;
}
.experienceDuration {
  font-size: 0.8rem;
}
.experienceContainers {
  min-width: 100%;
  margin-top: 1rem;
}
.colorLead {
  color: skyblue;
}
.colorCloud {
  color: #F89C1C;
}
.colorDev {
  color: rgb(144, 238, 144);
}
#legend {
  font-size: 2rem;
  margin-top: 3rem;
}
</style>