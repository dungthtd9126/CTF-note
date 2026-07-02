# Patch script

**This is in development. If you have any suggestions, try contact wtih me**

I used AI to gen this script so it may unstable

- Try command:
```
 ./patch.sh ./binary_file ./libs 
```
- Output 
```
patched:     /home/ctf/challenge_patched
loader:      /home/ctf/libs/ld-2.27.so <ld_version>
RPATH:       /home/ctf/libs
```

Usage:
Automatically patch a given **binary_file** with existed folder **libs** that contain all neccessary files to patch

You can get libs folder by copy from container to local and rename it as **libs**

- In my case, copy all files in folder **/lib/x86_64-linux-gnu**

Use this script when pwninit got errors with library files

Example:
```python
 @ctf ldd challenge_patched
./challenge_patched: ././libs/libc.so.6: version `GLIBC_ABI_DT_X86_64_PLT' not found (required by /usr/lib/librt.so.1)
./challenge_patched: ././libs/libc.so.6: version `GLIBC_ABI_DT_RELR' not found (required by /usr/lib/librt.so.1)
	linux-vdso.so.1 (0x00007fe0e1dca000)
	libbsd.so.0 => ././libs/libbsd.so.0 (0x00007fe0e1200000)
	libc.so.6 => ././libs/libc.so.6 (0x00007fe0e0e00000)
	librt.so.1 => /usr/lib/librt.so.1 (0x00007fe0e1d91000)
	./ld-2.27.so => /usr/lib64/ld-linux-x86-64.so.2 (0x00007fe0e1dcc000)
```
