<script>
	import { Button, Layout, Menu } from '$lib/'

	let collapsed = false
</script>

<Layout style="height:100%;">
	<Layout.Sider slot="outer-sider-left" {collapsed}>
		<Menu
			mode="inline"
			defaultSelectedKey="nav5"
			defaultOpenKey="menu2"
			style="border: 1px solid #f0f0f0;"
		>
			<Menu.Item key="nav4" icon="email" title="Nav4" />
			<Menu.SubMenu key="menu1" title="Menu1" icon="settings">
				<Menu.Item key="nav5" sub="menu1" title="Nav5" />
				<Menu.Item key="nav6" sub="menu1" title="Nav6" />
			</Menu.SubMenu>
			<Menu.SubMenu key="menu2" title="Menu2" icon="dashboard">
				<Menu.Item key="nav7" sub="menu2" title="Nav7" />
				<Menu.Item key="nav8" sub="menu2" title="Nav8" />
			</Menu.SubMenu>
		</Menu>
	</Layout.Sider>
	<Layout slot="inner-layout" style="height:100%;">
		<Layout.Header slot="header"
			><Button
				style="color: #ffffff;margin-right:8px;"
				icon="menu"
				type="text"
				shape="circle"
				on:click={() => (collapsed = !collapsed)}
			/>Svelteponents the port of Antd</Layout.Header
		>
		<Layout.Content slot="content"><slot /></Layout.Content>
	</Layout>
</Layout>
