<template>
  <q-page padding class="docs-input row justify-center">
    <div style="width: 500px; max-width: 90vw;">
      <p class="caption">Standard</p>
      <q-toggle v-model="check1" />

      <p class="caption">With label</p>
      <q-toggle v-model="check2" color="secondary" label="Tick me" />

      <p class="caption">With label on left side</p>
      <q-toggle v-model="check3" color="amber" label="Tick me" left-label />

      <p class="caption">With custom icons</p>
      <q-toggle
        v-model="check4"
        checked-icon="sentiment very satisfied"
        unchecked-icon="sentiment very dissatisfied"
      />
      <q-toggle
        v-model="check5"
        checked-icon="visibility"
        unchecked-icon="visibility_off"
        style="margin-left: 25px"
      />

      <p class="caption">With Array as model</p>
      <q-chip square color="secondary">Model: {{ checkArray }}</q-chip>
      <br><br>
      <q-toggle v-model="checkArray" label="One" color="yellow" val="one" />
      <q-toggle v-model="checkArray" label="Two" val="two" color="secondary" style="margin-left: 10px" />
      <q-toggle v-model="checkArray" label="Three" val="three" color="red" style="margin-left: 10px" />

      <p class="caption">
        With custom model values
        <span class="chip-container">
          <q-chip square color="secondary">
            Model: "{{ customModel }}"
          </q-chip>
        </span>
      </p>
      <q-toggle
        v-model="customModel"
        color="secondary"
        label="Do you agree with the terms & conditions?"
        true-value="yes"
        false-value="no"
      />

      <p class="caption">Keep color for unchecked state</p>
      <q-toggle keep-color v-model="check2" color="amber" label="Keeping color" />

      <p class="caption">Readonly</p>
      <q-toggle readonly v-model="check1" label="Readonly" />

      <p class="caption">Disabled</p>
      <q-toggle disable v-model="check1" label="Disabled" />

      <p class="caption">As Option Group in a Field</p>
      <q-field
        icon="vibration"
        helper="Select which notifications you want to receive"
        label="Notifications"
      >
        <q-option-group
          type="toggle"
          color="secondary"
          v-model="group"
          :options="[
            { label: 'Battery too low', value: 'bat' },
            { label: 'Friend request', value: 'friend' },
            { label: 'Picture uploaded', value: 'upload', color: 'red' }
          ]"
        />
      </q-field>

      <p class="caption">On a dark background</p>
      <div class="dark-example">
        <q-toggle dark v-model="check2" color="amber" label="Toggle me" class="q-my-md" />
        <q-field
          icon="vibration"
          helper="Select which notifications you want to receive"
          label="Notifications"
        >
          <q-option-group
            dark
            type="toggle"
            color="secondary"
            v-model="group"
            :options="[
              { label: 'Battery too low', value: 'bat' },
              { label: 'Friend request', value: 'friend' },
              { label: 'Picture uploaded', value: 'upload', color: 'red' }
            ]"
          />
        </q-field>
      </div>

      <p class="caption">In a list</p>
      <q-list link>
        <q-item tag="label">
          <q-item-main>
            <q-item-tile title>Notification</q-item-tile>
          </q-item-main>
          <q-item-side right>
            <q-toggle v-model="list1" />
          </q-item-side>
        </q-item>
        <q-item tag="label">
          <q-item-main>
            <q-item-tile label>Notification</q-item-tile>
            <q-item-tile sublabel>Allow notification</q-item-tile>
          </q-item-main>
          <q-item-side right>
            <q-toggle color="secondary" v-model="list2" />
          </q-item-side>
        </q-item>
        <q-item multiline tag="label">
          <q-item-main>
            <q-item-tile label>Notification</q-item-tile>
            <q-item-tile sublabel lines="2">Allow notifications Allow notifications Allow notifications Allow notifications Allow notifications</q-item-tile>
          </q-item-main>
          <q-item-side right>
            <q-toggle color="amber" v-model="list3" />
          </q-item-side>
        </q-item>
      </q-list>
    </div>
  </q-page>
</template>

<script>
import './docs-input.styl'

export default {
  data () {
    return {
      check1: false,
      check2: true,
      check3: true,
      check4: true,
      check5: false,
      checkArray: ['one'],
      check6: true,
      customModel: 'no',
      group: ['upload'],
      list1: false,
      list2: true,
      list3: true
    }
  }
}
</script>
