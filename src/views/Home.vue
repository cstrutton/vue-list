<template>
  <div>
    <v-card max-width="600" class="mx-auto">
      <v-fab-transition>
        <v-btn
          color="pink"
          fab
          dark
          absolute
          bottom
          right
          @click="addItem(newItem)"
        >
          <v-icon>mdi-plus</v-icon>
        </v-btn>
      </v-fab-transition>
      <v-toolbar color="light-blue" dark>
        <v-app-bar-nav-icon />
        <v-toolbar-title>Item List</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </v-toolbar>
      <v-list two-line>
        <v-list-item
          v-for="item in items"
          :key="item.id"
          @click="itemClick(item.id)"
        >
          <v-list-item-avatar>
            <v-icon
              :class="[item.iconClass]"
              v-text="item.icon"
            ></v-icon>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title v-text="item.title"></v-list-item-title>
            <v-list-item-subtitle v-text="item.content"></v-list-item-subtitle>
          </v-list-item-content>

          <v-list-item-action>
            <v-btn icon>
              <v-icon color="grey lighten-1">mdi-information</v-icon>
            </v-btn>
          </v-list-item-action>
        </v-list-item>
      </v-list>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data: () => ({
    selectedItem: null,
    newItem: {
      id: null,
      icon: 'mdi-folder',
      iconClass: 'grey lighten-1 white--text',
      title: '',
      content: ''
    },

    items: [
      {
        id: 0,
        icon: 'mdi-folder',
        iconClass: 'grey lighten-1 white--text',
        title: 'Photos',
        content: 'Jan 9, 2014'
      },
      {
        id: 1,
        icon: 'mdi-folder',
        iconClass: 'grey lighten-1 white--text',
        title: 'Recipes',
        content: 'Jan 17, 2014'
      },
      {
        id: 2,
        icon: 'mdi-folder',
        iconClass: 'grey lighten-1 white--text',
        title: 'Work',
        content: 'Jan 28, 2014'
      }
    ]
  }),
  methods: {
    itemClick(selectedItem) {
      this.selected = selectedItem
    },
    addItem(item) {
      item.id = this.items.length
      const today = new Date()
      item.content = today.toDateString()
      this.items.push(item)
    }
  }
}
</script>
