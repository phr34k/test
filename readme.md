
repro steps:

install flutter sdk locally on machine and run the calc/example, flutter uses junction/symlinks during I believe snapcraft can't handle them well. 

snapcraft stage source --use-lxd --verbosity debug
snapcraft stage websocket --use-lxd --verbosity debug
snapcraft stage packages --use-lxd --verbosity debug
snapcraft stage liquid terminal --use-lxd --verbosity debug

cd packages/calc/example
flutter build linux
snapcraft stage liquid terminal --use-lxd --verbosity debug
