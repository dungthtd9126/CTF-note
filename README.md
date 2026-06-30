# CTF-note

## File structure
```c
struct _IO_FILE
{
  int _flags;                    // 0x00
                                  /* High-order word is _IO_MAGIC; rest is flags. */
  /* padding */                   // 0x04 - 0x07

  /* The following pointers correspond to the C++ streambuf protocol. */
  char *_IO_read_ptr;             // 0x08
                                  /* Current read pointer */
  char *_IO_read_end;             // 0x10
                                  /* End of get area. */
  char *_IO_read_base;            // 0x18
                                  /* Start of putback+get area. */

  char *_IO_write_base;           // 0x20
                                  /* Start of put area. */
  char *_IO_write_ptr;            // 0x28
                                  /* Current put pointer. */
  char *_IO_write_end;            // 0x30
                                  /* End of put area. */

  char *_IO_buf_base;             // 0x38
                                  /* Start of reserve area. */
  char *_IO_buf_end;              // 0x40
                                  /* End of reserve area. */

  /* The following fields are used to support backing up and undo. */
  char *_IO_save_base;            // 0x48
                                  /* Pointer to start of non-current get area. */
  char *_IO_backup_base;          // 0x50
                                  /* Pointer to first valid character of backup area */
  char *_IO_save_end;             // 0x58
                                  /* Pointer to end of non-current get area. */

  struct _IO_marker *_markers;    // 0x60

  struct _IO_FILE *_chain;        // 0x68

  int _fileno;                    // 0x70
  int _flags2;                    // 0x74

  __off_t _old_offset;            // 0x78
                                  /* This used to be _offset but it's too small. */

  /* 1+column number of pbase(); 0 is unknown. */
  unsigned short _cur_column;     // 0x80
  signed char _vtable_offset;     // 0x82
  char _shortbuf[1];              // 0x83

  /* padding */                   // 0x84 - 0x87

  _IO_lock_t *_lock;              // 0x88

#ifdef _IO_USE_OLD_IO_FILE
};
```

## github command

Connect local terminal to github for remote updates:
```bash
git remote add origin https://github.com/dungthtd9126/CTF-event.git
```
- **git remote add**: This tells Git, "I want to create a new connection to a remote server."

- **origin**: This is just a shortcut name. Instead of making you type out the long GitHub URL every single time you want to push or pull code, Git lets you save it under a nickname. origin is the standard, universally used nickname for your main repository.

- **[https://github.com/dungthtd9126/CTF-event.git](https://github.com/dungthtd9126/CTF-event.git)**: This is the exact destination URL being attached to the nickname "origin".

Update tracking file / folder
```
git add .
```

Push changes to github
```
git push origin master
```
- **git push**: The action ("Upload my local saves...")

- **origin**: The destination ("...to the remote GitHub server we nicknamed 'origin'...")

- **master**: The specific data to send ("...and specifically upload the timeline of code I have on my master branch.")

## Modify partition and disk space
```
 sudo gparted &
```
## enter daila env
```
source daila_env/bin/activate
```

## set visualize max chunk size
```
set max-visualize-chunk-size 0x500
```

## Unikey tool on arch
```
Enable unikey arch tool: fcitx5-configtool
```
## update all packages
```
paru -Syu
```

## firejail 
```
firejail --private ./your_exploit_binary
```
## scan virus
```
clamscan -r ~/Downloads
```
## Clear all images and containers
```
docker system prune -a --volumes
```
