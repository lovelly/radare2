files = [
  'anal_tp.c',
  'asm.c',
  'p/core_anal.c',
  'blaze.c',
  'canal.c',
  'carg.c',
  'cbin.c',
  'cconfig.c',
  'cio.c',
  'cmd.c',
  #'cmd_anal.c',
  'cmd_api.c',
  #'cmd_cmp.c',
  #'cmd_debug.c',
  #'cmd_egg.c',
  #'cmd_eval.c',
  #'cmd_flag.c',
  #'cmd_hash.c',
  #'cmd_help.c',
  #'cmd_info.c',
  #'cmd_log.c',
  'cmd_macro.c',
  'cmd_magic.c',
  #'cmd_meta.c',
  #'cmd_mount.c',
  #'cmd_open.c',
  #'cmd_print.c',
  #'cmd_project.c',
  #'cmd_quit.c',
  #'cmd_search.c',
  #'cmd_search_rop.c',
  #'cmd_section.c',
  #'cmd_seek.c',
  #'cmd_type.c',
  #'cmd_write.c',
  #'cmd_zign.c',
  'core.c',
  'cundo.c',
  'disasm.c',
  'file.c',
  'fortune.c',
  'gdiff.c',
  'graph.c',
  'hack.c',
  'libs.c',
  #'linux_heap_glibc.c',
  'log.c',
  'panels.c',
  'patch.c',
  'plugin.c',
  'project.c',
  'pseudo.c',
  'rtr.c',
  'task.c',
  'vasm.c',
  'visual.c',
  'vmarks.c',
  'vmenus.c',
  'yank.c'
]


includes =  ['../../shlr']
if host_machine.system() != 'windows'
  includes += ['../../shlr/heap/include']
endif

r_core = library('r_core', files,
  include_directories: [
    platform_inc,
    include_directories(includes)
  ],
  c_args: ['-DCORELIB=1'],
  link_with: [
    r_util, r_reg, r_syscall, r_search, r_cons, r_anal, r_socket, r_io, r_fs,
    r_lang, r_hash, r_flag, r_parse, r_egg, r_debug, r_magic, r_crypto, r_config,
    r_bin, r_asm, r_bp, libr_shlr
  ],
  dependencies: [platform_deps],
  install: true,
  implicit_include_directories: false
)

pkg = import('pkgconfig')
pkg.generate(libraries: [r_core],
             subdirs: 'libr',
             version: r2version,
             name: 'r_core',
             filebase: 'r_core',
             requires: [
               'r_util', 'r_reg', 'r_syscall', 'r_search', 'r_cons', 'r_anal', 'r_socket', 'r_io', 'r_fs',
               'r_lang', 'r_hash', 'r_flag', 'r_parse', 'r_egg', 'r_debug', 'r_magic', 'r_crypto', 'r_config',
               'r_bin', 'r_asm', 'r_bp'
             ],
             description: 'radare foundation libraries')
