<template>
  <v-container>
    <v-layout column>
      <main-header>Dividers</main-header>

      <core-title>
        In list
      </core-title>
      <core-section>
        <v-list two-line>
          <template v-for="index in 5">
            <v-list-item
              :key="index"
              ripple
            >
              <v-list-item-content>
                <v-list-item-title>Item</v-list-item-title>
                <v-list-item-subtitle>Some item</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
            <v-divider
              v-if="index + 1 <= 5"
              :key="`divider-${index}`"
            />
          </template>
        </v-list>
      </core-section>

      <core-title>
        Vertical
      </core-title>
      <core-section>
        <v-toolbar
          color="purple"
          dark
        >
          <v-toolbar-title>Title</v-toolbar-title>

          <v-divider
            class="mx-4"
            inset
            vertical
          />

          <span class="subheading">
            My Home
          </span>

          <v-spacer />

          <v-toolbar-items>
            <v-btn flat>
              News
            </v-btn>

            <v-divider vertical />

            <v-btn flat>
              Blog
            </v-btn>

            <v-divider vertical />

            <v-btn flat>
              Music
            </v-btn>

            <v-divider vertical />
          </v-toolbar-items>

          <v-app-bar-nav-icon />
        </v-toolbar>
      </core-section>

      <core-title>
        Vertical
      </core-title>
      <core-section>
        <v-layout justify-center>
          <v-flex
            xs12
            sm8
            md6
          >
            <v-card>
              <v-toolbar
                color="orange lighten-1"
                dark
              >
                <v-app-bar-nav-icon />

                <v-toolbar-title>Message Board</v-toolbar-title>

                <v-spacer />

                <v-btn icon>
                  <v-icon>mdi-magnify</v-icon>
                </v-btn>
              </v-toolbar>

              <v-list two-line>
                <template v-for="(item, index) in items">
                  <v-subheader
                    v-if="item.header"
                    :key="item.header"
                    inset
                  >
                    {{ item.header }}
                  </v-subheader>

                  <v-divider
                    v-else-if="item.divider"
                    :key="index"
                    inset
                  />

                  <v-list-item
                    v-else
                    :key="item.title"
                    avatar
                    ripple
                  >
                    <v-list-item-avatar>
                      <img :src="item.avatar">
                    </v-list-item-avatar>
                    <v-list-item-content>
                      <v-list-item-title v-text="item.title" />
                      <v-list-item-subtitle v-text="item.subtitle" />
                    </v-list-item-content>
                  </v-list-item>
                </template>
              </v-list>
            </v-card>
          </v-flex>
        </v-layout>
      </core-section>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    name: 'Dividers',

    data: () => ({
      items: [
        {
          header: 'Today',
        },
        { divider: true },
        {
          avatar: 'https://picsum.photos/250/300?image=660',
          title: 'Meeting @ Noon',
          subtitle:
            "<span class='text--primary'>Spike Lee</span> &mdash; I'll be in your neighborhood",
        },
        {
          avatar: 'https://picsum.photos/250/300?image=821',
          title: 'Summer BBQ <span class="grey--text text--lighten-1"></span>',
          subtitle:
            "<span class='text--primary'>to Operations support</span> &mdash; Wish I could come.",
        },
        {
          avatar: 'https://picsum.photos/250/300?image=783',
          title: 'Yes yes',
          subtitle:
            "<span class='text--primary'>Bella</span> &mdash; Do you have Paris recommendations",
        },
        {
          header: 'Yesterday',
        },
        { divider: true },
        {
          avatar: 'https://picsum.photos/250/300?image=1006',
          title: 'Dinner tonight?',
          subtitle:
            "<span class='text--primary'>LaToya</span> &mdash; Do you want to hang out?",
        },
        {
          avatar: 'https://picsum.photos/250/300?image=146',
          title: 'So long',
          subtitle:
            "<span class='text--primary'>Nancy</span> &mdash; Do you see what time it is?",
        },
        {
          header: 'Last Week',
        },
        { divider: true },
        {
          avatar: 'https://picsum.photos/250/300?image=1008',
          title: 'Breakfast?',
          subtitle:
            "<span class='text--primary'>LaToya</span> &mdash; Do you want to hang out?",
        },
        {
          avatar: 'https://picsum.photos/250/300?image=839',
          title:
            'Winter Porridge <span class="grey--text text--lighten-1"></span>',
          subtitle:
            "<span class='text--primary'>cc: Daniel</span> &mdash; Tell me more...",
        },
        {
          avatar: 'https://picsum.photos/250/300?image=145',
          title: 'Oui oui',
          subtitle:
            "<span class='text--primary'>Nancy</span> &mdash; Do you see what time it is?",
        },
      ],
    }),
  }
</script>
