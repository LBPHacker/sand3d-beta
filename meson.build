project('sand3d-beta', [ 'c', 'cpp' ])

executable(
	'sand3d',
	sources: [
		'sand3d-beta.cpp',
		'./glad/src/glad.c',
	],
	include_directories: include_directories(
		'.',
		'./stb',
		'./glad/include',
		'./FastNoiseLite/Cpp',
	),
	dependencies: [
		dependency('glm'),
		dependency('glfw3'),
	],
	override_options: [
		'cpp_std=c++17',
	],
)
