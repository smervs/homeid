<template>
  <q-toolbar class="toolbar" :class="$q.screen.gt.sm ? 'q-pl-xl q-pr-lg' : ''">
    <q-toolbar-title >
        <div v-if="$q.screen.lt.sm">
            <q-img
            src="~assets/logo.png"
            spinner-color="white"
            style="width: 120px"
            />
        </div>
        <div class="row content-center" v-if="$q.screen.sm || $q.screen.gt.sm">
            <q-btn flat dense icon="fas fa-search" class="text-grey-5 q-mr-sm"/>
            <q-input :dense="true" borderless placeholder="Search for..."/>
        </div>
    </q-toolbar-title>
    <div class="row justify-end">
        <div class="row q-mr-lg user-info">
            <q-img src="~assets/user.jpg" class="user q-mr-xs"/>
            <div class="self-center">
                <q-btn-dropdown :label="($q.screen.gt.sm) ? 'Mervin Villaceran' : ''" dropdown-icon="fas fa-angle-down" flat no-icon-animation>
                    <q-list>
                        <q-item clickable v-close-popup>
                        <q-item-section>
                            <q-item-label>My Profile</q-item-label>
                        </q-item-section>
                        </q-item>

                        <q-item clickable v-close-popup>
                        <q-item-section>
                            <q-item-label>Logout</q-item-label>
                        </q-item-section>
                        </q-item>
                    </q-list>
                </q-btn-dropdown>
            </div>
        </div>
        <div class="self-center">
            <q-icon name="far fa-bell" class="notification-icon">
                <q-badge color="cyan" floating rounded class="badge">1</q-badge>
            </q-icon>
        </div>
        <q-btn flat dense icon="las la-bars" class="gt-sm-hidden q-pl-md" v-if="$q.screen.lt.md" @click="onClick" />
    </div>
  </q-toolbar>
</template>

<script>
export default {
  name: 'NavToolbar',
  props: [ 'onClick' ]
}
</script>
