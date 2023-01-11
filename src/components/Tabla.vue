<template>
	<div class="Tabla">
		<!-- <h1>{{ msg }}</h1> -->
		<b-row>
            <b-col lg="6" />
			<b-col lg="5" class="my-1">
				<b-form-group
					label="Filtro"
					label-for="filter-input"
					label-cols-sm="3"
					label-align-sm="right"
					label-size="sm"
					class="mb-1"
				>
					<b-input-group size="sm">
						<b-form-input
							id="filter-input"
							v-model="filter"
							type="search"
							placeholder="Búsqueda"
						></b-form-input>

						<b-input-group-append>
							<b-button :disabled="!filter" @click="filter = ''"
								>Limpiar</b-button
							>
						</b-input-group-append>
					</b-input-group>
				</b-form-group>
			</b-col>
            <b-col lg="1" />
		</b-row>
        <b-row>
            <b-col lg="1" />
			<b-col lg="10" class="my-1">
                <b-table
                    hover
                    outlined
                    responsive=true
                    :items="registros"
                    :fields="campos"
                    :filter="filter"
                >
                </b-table>
			</b-col>
            <b-col lg="1" />
		</b-row>
	</div>
</template>

<script>
export default {
	name: "Tabla",
	props: {
		msg: String,
	},
	data() {
		return {
			registros: [
				{
					id: 1,
					title: "Titulo",
					link: "link",
					logo: "logo",
					descripcion: "desc",
					categoria: "Cat",
				},
				{
					id: 2,
					title: "Titulo",
					link: "link",
					logo: "logo",
					descripcion: "desc",
					categoria: "Cat",
				},
				{
					id: 3,
					title: "Titulo",
					link: "link",
					logo: "logo",
					descripcion: "desc",
					categoria: "Cat",
				},
			],
			campos: [
				{ key: "id", label: "ID", sortable: true },
				{ key: "title", label: "Nombre", sortable: true },
				{ key: "link", label: "Enlace", sortable: true },
				{ key: "logo", label: "Logo", sortable: true },
				{ key: "descripcion", label: "Descripción", sortable: true },
				{ key: "categoria", label: "Categoría", sortable: true },
			],
			filter: null,
		};
	},
	computed: {
		sortOptions() {
			// Create an options list from our fields
			return this.fields
				.filter((f) => f.sortable)
				.map((f) => {
					return { text: f.label, value: f.key };
				});
		},
	},
};
</script>