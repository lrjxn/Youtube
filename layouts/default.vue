<template>
<v-app>

  <nav>
    <v-app-bar class="mau" flat app clipped-left>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title class="font-weight-bold">
          <img src="../assets/youtube.png" alt="youtube" width="40px">
    </v-toolbar-title>

    <v-spacer></v-spacer>
      <v-text-field flat hide-details append-icon="mdi-magnify" placeholder="Search" outlined dense class="hidden-sm-and-down"></v-text-field>
            <v-btn fab dark small>
      <v-icon>mdi-microphone</v-icon>
      </v-btn>

    <v-spacer></v-spacer>
      <v-menu offsetY>
      </v-menu>

    <v-tooltip bottom>
      <template v-slot:activator="{ on }">
          <v-btn icon v-on="on"> <v-icon size="28">mdi-apps</v-icon></v-btn>
      </template>
    </v-tooltip>

    <v-tooltip bottom>
      <template v-slot:activator="{ on }">
        <v-btn icon v-on="on">
          <v-icon size="28">mdi-dots-vertical</v-icon></v-btn>
      </template>
    </v-tooltip>
            
    <v-btn ripple outlined elevation="2" color="rgb(0, 120, 188)"  >
      <v-icon size="20">mdi-account</v-icon>Sign in
    </v-btn>
    </v-app-bar>




     <v-navigation-drawer v-model="drawer" app :clipped="$route.name !== 'Watch'" :temporary="$route.name === 'Watch'" id="nav">
      <div tag="div" class="v-navigation-drawer__content" v-bar>
        <v-list dense nav class="py-0" tag="div">
          <v-list-item :class="{'hidden-lg-and-up': $route.name === 'Watch' ? false : true}">
            <v-app-bar-nav-icon @click="drawer = !drawer">
            </v-app-bar-nav-icon>
  
            <v-toolbar-title class="px-4"></v-toolbar-title>
          </v-list-item>

          <v-divider class="hidden-lg-and-up"></v-divider>
          <div v-for="parentItem in items" :key="parentItem.header">
            <v-subheader v-if="parentItem.header">{{ parentItem.header }}</v-subheader>

            <v-list-item v-for="(item) in parentItem.pages" :key="item.title" link class="mb-0" router :to="item.link" exactactive-class="active-item">
              <v-list-item-icon v-if="parentItem.header !== 'Subscriptions'">
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>
    
          <v-list-item-content>
          <v-list-item-title class="px-4">{{item.title}}</v-list-item-title>
         </v-list-item-content>
        </v-list-item>
       <v-divider class="mt-2 mb-2"></v-divider>
      </div>

      <span v-for="link in links" :key="link.text">
        <v-btn color="blue-grey" text small>{{ link.text }}</v-btn>   
      </span>
      </v-list>

      <div class="tm-footer"><v-icon size="18" >
        mdi-copyright</v-icon>2021 Google LLC</div>
      </div>
    </v-navigation-drawer>
  </nav><v-main><nuxt></nuxt></v-main>
  
  </v-app>
</template>


<script>

import videos from '../components/videos.vue'
export default {
  components: { videos },
  data: () => ({

    drawer: false,
    items: [
      {
        header: null,
        pages: [
          
    {title: 'Home', 
    icon: 'mdi-home' 
    },

    {title: 'Explore', 
    icon: 'mdi-compass-outline' 
    },

    {title: 'Subscriptions',
    icon: 'mdi-youtube-subscription'
    }
        ]
    },
    {header: null,
    pages: [

    {title: 'Library',
    icon: 'mdi-play-box-multiple'
    },

    {title: 'History',
    icon: 'mdi-history'
    },
      ]
      },

    {header: null,
    },

    {header: 'BEST FROM YOUTUBE',
    pages: [

    {title: 'Music',
    icon: 'mdi-music'
    },

    {title: 'Sports',
    icon: 'mdi-basketball'
    },

    {title: 'Gaming',
    icon: 'mdi-youtube-gaming'
    },

    {title: 'News',
    icon: 'mdi-newspaper'
    },

    {title: 'Live',
    icon: 'mdi-access-point'
    },

    {title: '360° Video',
    icon: 'mdi-panorama-variant'
    },
      ]
      },

    {pages: [
    {title: 'Browse channels',
    icon: 'mdi-plus-circle'
    },
    ]
    },
      
    {header: 'MORE FROM YOUTUBE',
    pages: [

    {title: 'Youtube Premium',
    icon: 'mdi-youtube'
    },

    {title: 'Live',
    icon: 'mdi-access-point'
    }
      ]
      },

    {header: null,
    pages: [

    {title: 'Setting',
    icon: 'mdi-cog'
    },

    {title: 'Report history',
    icon: 'mdi-flag'
    },

    {title: 'Help',
    icon: 'mdi-help-circle'
    },

    {title: 'Send feedback',
    icon: 'mdi-message-alert',
    }
      ] 
      }
    ],

    links: [
      { text: 'About' },
      { text: 'Press'},
      { text: 'Copyrignt' },
      { text: 'Contact us' },
      { text: 'Creators' },
      { text: 'Advertise' },
      { text: 'Developers' },
      { text: 'Terms' },
      { text: 'Privacy'},
      { text: 'Policy & Safety'},
      { text: 'Test new features' } 
    ],
header: null,
  }),

    
    
  mounted() {
    this.drawer = this.$vuetify.breakpoint.mdAndDown ? false : true
    this.drawer = this.$route.name === 'Watch' ? false : this.drawer
  }
}
</script>
<style scoped>
#wrapper {
   
    width: 650px  ;
    background-color: rgb(255, 255, 255);
}

html, body {
  color: lightgrey;
}

.mau {
  color: rgb(255, 255, 255);
  font-family: 'Roboto', sans-serif;
}

.tm-footer {
    position: absolute;
    bottom: 0px;
}

.font {
      font-size: 15px;
}

</style>