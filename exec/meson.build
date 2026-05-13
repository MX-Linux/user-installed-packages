
exec_files      = [
                    package_name,
                  ]

libexec_exec   = [
                    'uip-apt-install',
                    'uip-apt-update',
                  ]

install_data(
            exec_files,
            install_dir: get_option('bindir'),
            install_mode: 'rwxr-xr-x',
)

install_data(
            libexec_exec,
            install_dir:  get_option('libexecdir') /  package_name,
            install_mode: 'rwxr-xr-x',
)

install_symlink(
            'uip',
            install_dir : get_option('bindir') ,
            pointing_to : package_name
)
