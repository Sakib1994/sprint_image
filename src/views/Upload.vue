<template>
  <div class="about">
    <v-container>
      <v-row justify="center">
        <v-col sm="6">
          <v-form>
            <v-container>
              <v-row>
                <v-col cols="12">
                  <v-text-field
                    v-model="name"
                    label="Outlined"
                    outlined
                    clearable
                  ></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-file-input
                    chips
                    multiple
                    outlined
                    label="File input w/ chips"
                  ></v-file-input>
                </v-col>
                <v-col cols="12">
                  <v-btn class="mr-4" type="submit">
                    submit
                  </v-btn>
                  <v-btn @click="clear"> clear </v-btn>
                </v-col>
              </v-row>
            </v-container>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data: () => ({
    name: "",
  }),
};
</script>