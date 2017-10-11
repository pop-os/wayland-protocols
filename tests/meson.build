prog_scan_sh = find_program('scan.sh')
prog_scanner = find_program(dep_scanner.get_pkgconfig_variable('wayland_scanner'))

# Check that each protocol passes through the scanner
foreach protocol_file : protocol_files
	protocol_path = join_paths(wayland_protocols_srcdir, protocol_file)
	test_name = 'scan-@0@'.format(protocol_file.underscorify())
	test(test_name, prog_scan_sh,
	     args: protocol_path,
	     env: [
		     'SCANNER=@0@'.format(prog_scanner.path()),
	     ]
	)
endforeach
