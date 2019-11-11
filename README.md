NVDLAオープンソースソフトウェア

NVDLA

NVIDIAディープラーニングアクセラレータ（NVDLA）は、ディープラーニング推論アクセラレータを設計する標準的な方法を促進する無料のオープンアーキテクチャです。NVDLAはモジュラーアーキテクチャを採用しているため、スケーラブルで高度に設定可能で、統合と移植性を簡素化するように設計されています。NVDLAの詳細については、プロジェクトのWebページをご覧ください。

http://nvdla.org/

オンラインドキュメント

最新のNVDLA SWのドキュメントはこちらから入手できます。このREADMEファイルには、基本情報のみが含まれています。

カーネルモードドライバー

カーネルモードドライバー（KMD）は、Linuxのツリー外カーネルモジュールとしてサポートされています。ARM64上のLinux 4.13.3で検証されており、ほとんど、またはまったく変更せずに他のCPUアーキテクチャで動作することが期待されています。ドライバは、DMAバッファの割り当てと共有にDRMとGEM PRIMEを使用します。

Linux KMDの構築

make KDIR=<path_to_Linux_source> ARCH=arm64 CROSS_COMPILE=<path_to_toolchain>
ユーザーモードドライバーとテストアプリケーション

ユーザーモードドライバー（UMD）には、ランタイムライブラリが含まれています。ロード可能からネットワークをロードし、それをNVDLA KMDに送信するためのインターフェースを提供します。参考のため、このパッケージには、ランタイムインターフェイスの使用方法を示すテストアプリケーションも含まれています。

Linux UMDとテストアプリケーションの構築

export TOP=<path_to_umd>
make
免許

NVDLA SWは、BSD 3-Clauseライセンスの下でリリースされています。GPLv2 / BSD 3-ClauseデュアルライセンスでリリースされるNVDLA SW Linuxカーネルモードドライバーには例外があります。各ソースファイルとヘッダーファイルには、ファイルの先頭にライセンス通知が含まれています。

NVDLA SWは、フラットバッファ、半精度ライブラリなどの外部ソフトウェアコンポーネントを使用します。これらのソフトウェアのライセンステキストは、COPYINGファイルに含まれています。









# NVDLA Open Source Software

## NVDLA

The NVIDIA Deep Learning Accelerator (NVDLA) is a free and open architecture that promotes
a standard way to design deep learning inference accelerators. With its modular architecture,
NVDLA is scalable, highly configurable, and designed to simplify integration and portability.
Learn more about NVDLA on the project web page.

<http://nvdla.org/>

## Online Documentation

You can find the latest NVDLA SW documentation [here](http://nvdla.org/sw/contents.html).
This README file contains only basic information.

## Kernel Mode Driver

The kernel mode driver (KMD) is supported as a Linux out-of-tree kernel module.
It has been verified with Linux 4.13.3 on ARM64 and is expected to work
on other cpu architectures with little or no modification.
The driver uses DRM and GEM PRIME for DMA buffer allocation and sharing.

### Building the Linux KMD
    make KDIR=<path_to_Linux_source> ARCH=arm64 CROSS_COMPILE=<path_to_toolchain>

## User Mode Driver and test application

The user mode driver (UMD) includes runtime library. It provides interfaces to load
network from loadable and submit it to NVDLA KMD. For reference, this package also
includes test application demonstrating usage of runtime interfaces.

### Building the Linux UMD and test application
    export TOP=<path_to_umd>
    make

## Licensing

NVDLA SW is released under the BSD 3-Clause license.
An exception exists for the NVDLA SW Linux Kernel Mode Driver which is released
under a GPLv2/BSD 3-Clause dual license.
Each source and header file contains its license notice at the start of the file.

NVDLA SW uses some external software components such as flatbuffers, half-precision library.
License text for these softwares is included in COPYING file.
