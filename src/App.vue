<template>
  <Container>
    <AdvantagesList :link="information.link" :title="information.title" :sub-title="information.subTitle"
      :description="information.description" :items="items" />
    <AdvantagesList :title="information.title" :items="itemsTwo" />
    <AdvantagesList :title="information.title" :items="itemsThree" />
    <AdvantagesList :title="information.title" :items="itemsFour" />

  </Container>
</template>

<script>
  import AdvantagesList from './patterns/AdvantagesList'
  import Container from './components/Container'


  export default {
    name: 'App',
    data() {
      return {
        information: {
          title: 'Acronis Cyber Disaster Recovery Cloud',
          subTitle: 'Sync and Share',
          description: 'A turnkey, self-service solution that lets you protect your customers’ workloads by recovering their IT systems and applications utilizing the Acronis cloud infrastructure.',
          link: '#'
        },
         itemsFour: [{
            icon: 'advantagesOne',

            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          },
          {
            icon: 'advantagesOne',

            description: `<a href="#">With Acronis Files Connect</a>, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.`
          },
        ],
         itemsThree: [{
            name: 'AFP Connection to File Shares',
            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          },
          {
            name: 'AFP Connection to File Shares',
            description: `<a href="#">With Acronis Files Connect</a>, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.`
          },
        ],
        itemsTwo: [{
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          },
          {
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: `<a href="#">With Acronis Files Connect</a>, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.`
          },
        ],
        items: [{
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          },
          {
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: `<a href="#">With Acronis Files Connect</a>, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.`
          },
          {
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          },
          {
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          },
          {
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          },
          {
            icon: 'advantagesOne',
            name: 'AFP Connection to File Shares',
            description: 'With Acronis Files Connect, Macs connect to and mount file shares on Windows file servers and NAS as native AFP volumes. This allows Mac users to continue using the same tools.'
          }
        ]
      }
    },
    components: {
      AdvantagesList,
      Container
    }
  }
</script>

<style lang="scss">
  @import "~assets/scss/config";
  @import "~assets/scss/reset";
  @import "~assets/scss/mixins";
  @import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,600;0,700;0,800;1,300;1,400;1,600;1,700;1,800&display=swap');

  body {
    height: 100%;
    margin: 0;
    padding: 0;
    font: normal 16px/24px "Open Sans", sans-serif;
    color: color(main);
  }

  a {
    text-decoration: none;
  }

  svg {
    display: block;
  }
</style>