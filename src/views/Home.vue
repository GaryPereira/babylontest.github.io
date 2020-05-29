<template>
  <div class=Home>
    <div class="Play">
      <Scene>
        <property name="clearColor" color="#000000"></property>
        <Camera type="follow"></Camera>
        <Entity :position="[0, 0, 5]">
          <Animation property="rotation.x" :duration="5">
            <Key frame="0%" :value="0"></Key>
            <Key frame="100%" :value="Math.PI * 2"></Key>
          </Animation>
          <Animation property="rotation.y" :duration="5" :end="Math.PI * 2"></Animation>
          <Animation property="rotation.z" :duration="5" :end="Math.PI * 2"></Animation>
          <PointLight diffuse="#FF0000"></PointLight>
          <template v-for="x in [0, 4, -4]">
            <template v-for="y in [0, 4, -4]">
              <Asset src="https://www.babylonjs-playground.com/scenes/skull.babylon" :scaling="[0.02, 0.02, 0.02]" v-for="z in [0, 4, -4]" :position="[x, y, z]" :key="`${x},${y},${z}`"></Asset>
            </template>
          </template>
        </Entity>
      </Scene>
    </div>
    <div class="Top">
      <v-app id="inspire">
        <v-content>
          <v-container
            class="fill-height"
            fluid
          >
            <v-row
              align="center"
              justify="center"
            >
              <v-col
                cols="12"
                sm="8"
                md="4"
              >
                <v-card class="elevation-12">
                  <v-toolbar
                    color="primary"
                    dark
                    flat
                  >
                    <v-toolbar-title>Login form</v-toolbar-title>
                    <v-spacer></v-spacer>
                  </v-toolbar>
                  <v-card-text>
                    <v-form>
                      <v-text-field
                        label="Login"
                        name="login"
                        prepend-icon="mdi-account"
                        type="text"
                      ></v-text-field>

                      <v-text-field
                        id="password"
                        label="Password"
                        name="password"
                        prepend-icon="mdi-lock"
                        type="password"
                      ></v-text-field>
                    </v-form>
                  </v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="primary">Login</v-btn>
                  </v-card-actions>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-content>
      </v-app>
    </div>
  </div>
</template>


<style>

.Play{
  position: absolute;
  width: 100%;
  height: 100%;
}

</style>
