<template>
	<div>
		<container>
			<navbar>
				<a v-link='{"name":"demo"}'><icon type="arrow-left"></icon></a>
				<span class="split"></span>
				<span>Input</span>
			</navbar>
			<content>
				<group-title>text</group-title>
				<input-text default-value="peter">
					<label slot>username:</label>
				</input-text>
				<group-title>password</group-title>
				<input-text type="password" placeholder="请输入密码">
					<label slot>password:</label>
				</input-text>
				<group-title>number</group-title>
				<input-text type="number" placeholder="请输入数字">
					<label slot>数量:</label>
				</input-text>
				<group-title>phone</group-title>
				<input-text type="phone" placeholder="电话号码">
					<label slot>手机:</label>
				</input-text>

				<group-title>disabled</group-title>
				<input-text placeholder="disabled" :disabled="disabled" value="这是只读输入框">
					<label slot>不可编辑:</label>
				</input-text>

				<group-title>clear icon</group-title>
				<input-text placeholder="可以清除内容" clearable>
					<label slot>clear:</label>
				</input-text>

				<group-title>status</group-title>
				<input-text state='success'>
					<label slot>success:</label>
				</input-text>
				<input-text state='warning'>
					<label slot>warning:</label>
				</input-text>
				<input-text state='error'>
					<label slot>error:</label>
				</input-text>

				<group-title>multiple icon</group-title>
				<input-text state='warning' clearable>
					<label slot>warning:</label>
				</input-text>

				<group-title>onchange</group-title>
				<input-text :on-change="onChangeHandle">
					<label slot>input:</label>
				</input-text>

				<group>
					<group-item pure>
						<btn style="secondary" block @click="disableChangeHandle">取消</btn>
					</group-item>
				</group>
			</content>
		</container>
	</div>
</template>


<script>
	import { Container, Content, Navbar, Group, GroupItem, GroupTitle, InputText, Btn, Icon } from '../components/index.js';

	export default {
		components: {
		  	Container,
		  	Content,
		  	Navbar,
		    Group,
		    GroupItem,
		    GroupTitle,
		    InputText,
		    Btn,
		    Icon
		},
		data(){
			return {
				disabled: true
			};
		},
		methods: {
			onChangeHandle(event, value){
				console.log(event, value);
			},
			disableChangeHandle(){
				this.disabled = !this.disabled;
			}
		}
	};
</script>