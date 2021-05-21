<template>
  <q-page class="q-pa-xl">
      <div class="row full-width">
          <div class="col-grow">
              <div class="text-h5 text-weight-medium">
                My save search
                <q-badge color="white" text-color="cyan" rounded class="text-h6 text-weight-bold">5</q-badge>
              </div>
              <div class="text-subtitle2 text-grey-7">
                  Lorem ipsum dolor sit amet, consec tetur cing elit. Suspe ndisse suscipit
              </div>
          </div>
          <div>
            <q-input outlined placeholder="Search listing" bg-color="white">
              <template v-slot:prepend >
                <q-icon name="fas fa-search" class="listing-search"/>
              </template>
            </q-input>
          </div>
      </div>
      <div class="full-width q-mt-xl">
          <q-table flat bordered hide-pagination no-hover
            :data="data"
            :columns="columns"
            row-key="name"
            class="listing-table"
          >
            <template v-slot:header="props">
                <q-tr :props="props" no-hover>
                    <q-th
                        v-for="col in props.cols"
                        :key="col.name"
                        :props="props"
                        class="table-header-rows"
                    >
                    {{ col.label }}
                    </q-th>
                </q-tr>
            </template>
            <template v-slot:body="props">
                <q-tr :props="props" class="table-row">
                    <q-td key="current_package" :props="props">
                        {{ props.row.current_package }}
                    </q-td>
                    <q-td key="properties_remaining" :props="props">
                        {{ props.row.properties_remaining }}
                    </q-td>
                    <q-td key="featured_remaining" :props="props">
                        {{ props.row.featured_remaining }}
                    </q-td>
                    <q-td key="renewal_remaining" :props="props">
                        {{ props.row.renewal_remaining }}
                    </q-td>
                    <q-td key="storage_space" :props="props">
                        {{ props.row.storage_space }}
                    </q-td>
                    <q-td key="expiry_date" :props="props">
                        {{ props.row.expiry_date }}
                    </q-td>
                </q-tr>
            </template>
          </q-table>
      </div>
      <div class="row full-width justify-end q-mt-lg">
          <q-btn color="cyan" text-color="white" label="Change Package" padding="md xl" class="no-shadow" />
      </div>
  </q-page>
</template>

<script>
const columnClasses = 'text-body1 text-grey-7 table-row';

export default {
  name: 'PageIndex',
  data () {
    return {
      columns: [
        { name: 'current_package', align: 'left', label: 'Current Package', field: 'current_package', style: 'padding: 30px 40px;', classes: `${columnClasses} text-weight-bold` },
        { name: 'properties_remaining', align: 'left', label: 'Properties Remanining', field: 'properties_remaining', classes: columnClasses },
        { name: 'featured_remaining', align: 'left', label: 'Featured Remaining', field: 'featured_remaining', classes: columnClasses },
        { name: 'renewal_remaining', align: 'left', label: 'Renewal Remaining', field: 'renewal_remaining', classes: columnClasses },
        { name: 'storage_space', align: 'left', label: 'Storage Space', field: 'storage_space', classes: columnClasses },
        { name: 'expiry_date', align: 'left', label: 'Expiry Date', field: 'expiry_date', classes: columnClasses },
      ],
      data: [
        {
          current_package: 'Free',
          properties_remaining: 0,
          featured_remaining: 3,
          renewal_remaining: 'For Rent',
          storage_space: '2 MB / 20 MB',
          expiry_date: '30 December, 2019',
        },
        {
          current_package: 'Free',
          properties_remaining: 0,
          featured_remaining: 3,
          renewal_remaining: 'For Rent',
          storage_space: '2 MB / 20 MB',
          expiry_date: '30 December, 2019',
        },
        {
          current_package: 'Free',
          properties_remaining: 0,
          featured_remaining: 3,
          renewal_remaining: 'For Rent',
          storage_space: '2 MB / 20 MB',
          expiry_date: '30 December, 2019',
        },
        {
          current_package: 'Free',
          properties_remaining: 0,
          featured_remaining: 3,
          renewal_remaining: 'For Rent',
          storage_space: '2 MB / 20 MB',
          expiry_date: '30 December, 2019',
        },
        {
          current_package: 'Free',
          properties_remaining: 0,
          featured_remaining: 3,
          renewal_remaining: 'For Rent',
          storage_space: '2 MB / 20 MB',
          expiry_date: '30 December, 2019',
        },
      ]
    }
  }
}
</script>
