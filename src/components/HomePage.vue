<template>
  <div class="dashboard">
    <profile
      name="Dinesh.S"
      designation="Software Developer"
      description="Hello! 
      I'm a normal person in this world trying to survive. 
      Currently surviving by developing android apps.
       I started my journey towards mobile app development by taking courses from Udemy. 
       Then I applied that knowledge to solve some industrial problems with the help of Origa Labs (Last company I worked with) and of course, 
       I gained some knowledge from my colleagues."
      phone="+91 8778839742"
      email="dineshsaratha8@gmail.com"
    ></profile>
    <timeline
      title="Work Experience"
      :timeline_data="[
        {
          yearStart: 'Oct 2018',
          yearEnd: 'Nov 2019',
          data: [
            'Software Engineer',
            'Armstrong Labs Private Limited',
            'Developed Application for AR Device'
          ]
        },
        {
          yearStart: 'Jul 2018',
          yearEnd: 'Sep 2018',
          data: [
            'Trainee Software Engineer',
            'Armstrong Labs Private Limited',
            'Learned about AR device (RealWear), Developed SAT(Site Acceptance Testing) application and QC(Quality Checking) application'
          ]
        }
      ]"
    ></timeline>
    <timeline
      title="Education"
      :timeline_data="[
        {
          yearStart: '2014',
          yearEnd: '2018',
          data: [
            'B.E Computer Science',
            'Sri Ramakrishna Institute of Technology',
            'Passed out with 65%'
          ]
        },
        {
          yearStart: '2014',
          yearEnd: '2014',
          data: ['HSC', 'Sowdambikaa M.H.S.S', 'Passed out with 92%']
        },
        {
          yearStart: '2012',
          yearEnd: '2012',
          data: ['SSLC', 'Sowdambikaa M.H.S.S', 'Passed out with 90%']
        }
      ]"
    ></timeline>

    <timeline
      title="Project Activities"
      :timeline_data="[
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'UnPhishMe',
            'Languages Used: Java',
            'An App for detecting phishing attacks in smartphone'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/UnPhishMe'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Tic-Tac-Toe',
            'Languages Used: Java',
            'Dual Player Tic-Tac-Toe game'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/tic_tac_toe'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Brain Trainer',
            'Languages Used: Java',
            'For increasing addition speed of child'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/BrainTrainer'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Weather Info',
            'Languages Used: Java',
            'Type the city name to get weather info'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/WeatherInfo'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Guess the number',
            'Languages Used: Java',
            'Guess the correct number that is guessed by the computer'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/GuessTheNumber'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'French Dictation',
            'Languages Used: Java',
            'Learn French dictation through English'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/PhrasesDictation'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Currency Convertor',
            'Languages Used: Java',
            'Converts Indian Rupee to Dollors'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/Currency-Convert'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Guess Celebrity',
            'Languages Used: Java',
            'Guess the celebrity that is shown in the image'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/GuessCeleb'
          }
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Video Crop Sample',
            'Languages Used: Java',
            'Video Cropping Code Sample using FFmpeg and FFprobe commands'
          ],
          footer: {
            github: 'https://github.com/Dinesh41/VideoCrop'
          }
        }
      ]"
    ></timeline>

    <timeline
      title="Source of Knowledge"
      :timeline_data="[
        {
          yearStart: '',
          yearEnd: '',
          data: ['Learn Vue 2: Step By Step Course', 'by Laracast']
        },
        {
          yearStart: '',
          yearEnd: '',
          data: ['Android Complete Developer Course', 'by Udemy']
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Java level 2 Qualification Certificate',
            'by Cambridge Certification Authoity'
          ]
        },
        {
          yearStart: '',
          yearEnd: '',
          data: [
            'Java level 1 Qualification Certificate',
            'by Cambridge Certification Authoity'
          ]
        },
        {
          yearStart: '',
          yearEnd: '',
          data: ['Completion of C++ Training', 'by Spoken Tutorial Projecr']
        }
      ]"
    ></timeline>
  </div>
</template>

<script>
import Timeline from "./Timeline.vue";
import Profile from "./Profile.vue";
export default {
  name: "HomePage",
  components: {
    Timeline,
    Profile
  },
  props: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
