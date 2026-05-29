
html_files      = [
                'license.html',
                ]

policy_files    = [
                'org.mxlinux.user-installed-packages.policy',
                ]

install_data(
        html_files,
        install_dir: get_option('datadir') / package_name
)

install_data(
        'bash-completion' / package_name,
        install_dir: get_option('datadir') / 'bash-completion' / 'completions'
)

merged_file = i18n.merge_file(
        input: 'org.mxlinux.user-installed-packages.policy',
        output: 'org.mxlinux.user-installed-packages.policy',
        type: 'xml',
        po_dir: '..' / subdir_po,
        data_dirs: ['../data'],
        install_dir: get_option('datadir') / 'polkit-1/actions',
        install: true,
)

i18n.merge_file(
    input: configure_file(
        input: '@0@.desktop'.format(desktop_id),
        output: '@0@.desktop.i18n'.format(desktop_id),
        capture: true,
        command: ['sed', '/^#/d', '@INPUT@']
        ),
    install: true,
    install_dir: get_option('datadir') / 'applications',
    output: '@0@.desktop'.format(desktop_id),
    po_dir: '..' / subdir_po,
    type: 'desktop',
)



