donut_dir = ../doughnut/web/node_modules/snowbrush/dist
brownie_dir = ../brownie/Browniejs/node_modules/snowbrush/dist

donut:
	npm run f-build; mkdir -p $(donut_dir); cp -a ./dist/snowbrush.js* $(donut_dir)

brownie:
	npm run f-build; mkdir -p $(brownie_dir); cp -a ./dist/snowbrush.js* $(brownie_dir)
