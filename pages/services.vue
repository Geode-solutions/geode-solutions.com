<template>
  <v-container>
    <v-row>
      <v-col>
        <h1 class="display-3 my-5 py-5" align="center">
          Custom-tailored services
        </h1>
        <h2 class="display-1 my-5 pb-5" align="center">
          <v-btn large color="primary" dark href="mailto:contact@geode-solutions.com">
            Contact us
          </v-btn>
        </h2>

        <v-card v-for="(service, index) in services" :key="index" style="margin-bottom: 40px">
          <v-row align="center" justify="space-around">
            <v-col :order-sm="(index + 1) % 2" cols="12" sm="5">
              <v-card-text>
                <v-lazy 
                  :options="{
                    threshold: .5
                  }"
                >
                  <v-img
                    :src="require('@/assets/services/'+service.image)"
                    :alt="'Geode-solutions '+ service.title"
                    contain
                  />
                </v-lazy>
              </v-card-text>
            </v-col>
            <v-col cols="12" sm="7">
              <v-card flat>
                <v-card-title primary-title class="justify-center display-1">
                  {{ service.title }}
                </v-card-title>
                <v-card-text align="justify" class="title">
                  {{ service.text }}
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-card>
        <h2 class="display-1 my-5 py-5" align="center">
          Let us know how we can help!
          <div class="my-2">
            <v-btn large color="primary" dark href="mailto:contact@geode-solutions.com">
              Contact us
            </v-btn>
          </div>
        </h2>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    services: [
      {
        title: 'OpenGeode integration',
        image: 'integration.jpg',
        text:
          'You would like to use OpenGeode environment, features and technologies within another software suite. \
          You are used to specific code and you need its features in an OpenGeode extension. \
          We offer you the possibility to integrate OpenGeode ecosystem, and your code, through other platform plugins.'
      },
      {
        title: 'Prototyping/Code development',
        image: 'idea.webp',
        text:
          'You need a technical solution to solve a dedicated problem. \
          You have precise needs on software development and features. \
          We propose you our skills and experience to design and develop \
          your solution from a working prototype to a full featured product.'
      },
      {
        title: 'Expertise and Consulting',
        image: 'success.webp',
        text:
          'You have specific questions or needs on meshing tasks or existing tools. \
            Our experts advices and skills will allow you to reach your objectives faster.'
      },
      {
        title: 'Education',
        image: 'pencil.jpg',
        text:
          'You need to learn how to work with OpenGeode platform and our products. \
            You ask for courses on modeling and meshing or on software development. \
            We can build together custom training program designed from your needs.'
      }
    ]
  }),
  head() {
    return {
      title: 'Geode-solutions custom-tailored services'
    }
  }
}
</script>
