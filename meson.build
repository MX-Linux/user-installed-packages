project('user-installed-packages', 
    meson_version: '>=1.0.0',
    version: configure_file(
        command: [
        'dpkg-parsechangelog', '-l', 
        meson.project_source_root() / 'debian/changelog',
        '-SVersion'],
        capture: true,
        output: 'version',
        )
)


i18n = import('i18n')

package_name    = meson.project_name()
desktop_id      = package_name
gettext_package = package_name

subdir_po      = 'translations/po'

subdir('data')

subdir('exec')

subdir('help')

subdir('icons')

subdir(subdir_po)

message('\n'.join(['',
'',
'    @0@ @1@'.format(meson.project_name(), meson.project_version()),
'',
'    Built-in options:',
'    prefix:                 @0@'.format(get_option('prefix')),
'    bindir:                 @0@'.format(get_option('bindir')),
'    datadir:                @0@'.format(get_option('datadir')),
'    libdir:                 @0@'.format(get_option('libdir')),
'    libexecdir:             @0@'.format(get_option('libexecdir')),
'    localedir:              @0@'.format(get_option('localedir')),
'    sysconfdir:             @0@'.format(get_option('sysconfdir')),
'',
'    Build options:',
'    source directory:       @0@'.format(meson.project_source_root()),
'    build  directory:       @0@'.format(meson.project_build_root()),
'',
]))
