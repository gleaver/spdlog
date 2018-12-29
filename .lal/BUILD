#!/usr/bin/env bash

set -ex

root=$(pwd)
input="${root}/INPUT"
output="${root}/OUTPUT"
build="${root}/BUILD"

component=$1
config=$2

fail() {
  echo $1 >&2 && exit 1
}

build() {
  mkdir -p "${build}"  
  cd "${build}"
  
  
  cmake -DCMAKE_INSTALL_PREFIX=${output} ..
  cd ${build}
  make spdlog-utests install/fast

  cd "${root}"
}

build
