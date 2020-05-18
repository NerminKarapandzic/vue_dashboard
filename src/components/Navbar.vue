<template lang="html">
	<nav>
		<v-app-bar flat app>
			<v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
			<v-toolbar-title class="text-uppercase grey--text">
				App title
			</v-toolbar-title>
			<v-spacer />
			<v-btn text color="grey darken-3">
				<v-icon left>exit_to_app</v-icon>
				<span>Sign out</span>
			</v-btn>
		</v-app-bar>
            
		<v-navigation-drawer v-model="drawer" app class="purple lighten-2">
            <v-layout column align-center class="mt-5">
                <v-flex class="mt-5">
                    <v-avatar size="100"  >
                        <img src="/avatar.jpg" alt="alt" style="border-radius:50%;">
                    </v-avatar>
                </v-flex>
                <p class="text-center white--text mt-2 subtitle-1">Nermin Karapandzic</p>
            </v-layout>
			<v-list>
				<v-list-item v-for="link in links" :key="link.text" router  :to="link.route">
					<v-list-item-action>
						<v-icon class="white--text">{{ link.icon }}</v-icon>
					</v-list-item-action>
					<v-list-item-content>
						<v-list-item-title class="white--text"> {{ link.text }} </v-list-item-title>
					</v-list-item-content>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>
	</nav>
</template>

<script>
export default {
	data() {
		return {
			drawer: false,
			links: [
				{ icon: "dashboard",text: "Dashboard",route: "/" },
				{icon: "folder",text: "My Projects",route: "/projects" },
				{icon: "person",text: "Team",route: "/team" },
			],
		};
	},
};
</script>

<style lang="css" scoped></style>
