# Hey! I'm Filing Here

In this UCLA CS111 lab, I implemented a 1 MiB ext2 file system with 2 directories, 1 regular file, and 1 symbolic link.

The filesystem uses 1 KiB sized blocks with space for 128 inodes. The root directory of the filesystem contains an empty directory `lost+found`, a symlink `hello`, and a file `hello-world`. The `hello` symlink points to the `hello-world` file, which contains the plaintext "Hello world\n". 

## Building
generate the ext2-create executable:
```
make
```

generate the cs111-base.img file:
```
./ext2-create
```



## Running

dump the filesystem information:
```
dumpe2fs cs111-base.img
```

check that the filesystem is correct:
```
fsck.ext2 cs111-base.img
```

create a directory and mount the filesystem:
```
mkdir mnt
sudo mount -o loop cs111-base.img mnt
```


## Cleaning up

unmount filesystem and delete directory:
```
sudo umount mnt
rmdir mnt
```

remove binaries:
```
make clean
```
