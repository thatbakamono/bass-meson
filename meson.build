project('bass', 'c', version: '2.4.16.7')

cc = meson.get_compiler('c')

if host_machine.system() == "windows"
	if host_machine.cpu_family() == "x86_64"
		bass_lib = cc.find_library('bass', dirs: meson.current_source_dir + '/lib/windows/x64')
	elif host_machine.cpu_family() == "x86"
		bass_lib = cc.find_library('bass', dirs: meson.current_source_dir + '/lib/windows/x86')
	else
		error("Only x86_64 and x86 are supported on Windows")
	endif
elif host_machine.system() == "linux"
	if host_machine.cpu_family() == "x86_64"
		bass_lib = cc.find_library('bass', dirs: meson.current_source_dir + '/lib/linux/x64')
	elif host_machine.cpu_family() == "x86"
		bass_lib = cc.find_library('bass', dirs: meson.current_source_dir + '/lib/linux/x86')
	else
		error("Only x86_64 and x86 are supported on Linux")
	endif
elif host_machine.system() == "darwin"
	if host_machine.cpu_family() == "x86_64"
		bass_lib = cc.find_library('bass', dirs: meson.current_source_dir + '/lib/macos/x64')
	else
		error("Only x86_64 is supported on MacOS")
	endif
else
	error("Only Windows, Linux and MacOS are supported")
endif

bass_dep = declare_dependency(
	dependencies: bass_lib, 
	include_directories: 'include/'
)