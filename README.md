# CTF-note

## File structure
```c
struct _IO_FILE_complete
{
  int _flags;                         // 0x00
                                       /* High-order word is _IO_MAGIC; rest is flags. */

  /* padding */                        // 0x04 - 0x07

  /* The following pointers correspond to the C++ streambuf protocol. */
  char *_IO_read_ptr;                  // 0x08
                                       /* Current read pointer */
  char *_IO_read_end;                  // 0x10
                                       /* End of get area. */
  char *_IO_read_base;                 // 0x18
                                       /* Start of putback+get area. */

  char *_IO_write_base;                // 0x20
                                       /* Start of put area. */
  char *_IO_write_ptr;                 // 0x28
                                       /* Current put pointer. */
  char *_IO_write_end;                 // 0x30
                                       /* End of put area. */

  char *_IO_buf_base;                  // 0x38
                                       /* Start of reserve area. */
  char *_IO_buf_end;                   // 0x40
                                       /* End of reserve area. */

  /* The following fields are used to support backing up and undo. */
  char *_IO_save_base;                 // 0x48
                                       /* Pointer to start of non-current get area. */
  char *_IO_backup_base;               // 0x50
                                       /* Pointer to first valid character of backup area */
  char *_IO_save_end;                  // 0x58
                                       /* Pointer to end of non-current get area. */

  struct _IO_marker *_markers;         // 0x60

  struct _IO_FILE *_chain;             // 0x68

  int _fileno;                         // 0x70
  int _flags2;                         // 0x74

  __off_t _old_offset;                 // 0x78
                                       /* This used to be _offset but it's too small. */

  /* 1+column number of pbase(); 0 is unknown. */
  unsigned short _cur_column;          // 0x80
  signed char _vtable_offset;          // 0x82
  char _shortbuf[1];                   // 0x83

  /* padding */                        // 0x84 - 0x87

  _IO_lock_t *_lock;                   // 0x88

  _IO_off64_t _offset;                 // 0x90

  /* Wide character stream stuff. */
  struct _IO_codecvt *_codecvt;        // 0x98
  struct _IO_wide_data *_wide_data;    // 0xa0
  struct _IO_FILE *_freeres_list;      // 0xa8
  void *_freeres_buf;                  // 0xb0

  size_t __pad5;                       // 0xb8

  int _mode;                           // 0xc0

  /* Make sure we don't get into trouble again. */
  char _unused2[20];                   // 0xc4 - 0xd7
};
```

### Flag bits
```c
/* Magic numbers and bits for the _flags field.
   The magic numbers use the high-order bits of _flags;
   the remaining bits are available for variable flags.
   Note: The magic numbers must all be negative if stdio
   emulation is desired. */

#define _IO_MAGIC              0xFBAD0000  /* Magic number */
#define _OLD_STDIO_MAGIC       0xFABC0000  /* Emulate old stdio. */
#define _IO_MAGIC_MASK         0xFFFF0000

#define _IO_USER_BUF           0x0001      /* User owns buffer; don't delete it on close. */
#define _IO_UNBUFFERED         0x0002
#define _IO_NO_READS           0x0004      /* Reading not allowed */
#define _IO_NO_WRITES          0x0008      /* Writing not allowed */
#define _IO_EOF_SEEN           0x0010
#define _IO_ERR_SEEN           0x0020
#define _IO_DELETE_DONT_CLOSE  0x0040      /* Don't call close(_fileno) on cleanup. */
#define _IO_LINKED             0x0080      /* Set if linked using _chain to _IO_list_all. */
#define _IO_IN_BACKUP          0x0100
#define _IO_LINE_BUF           0x0200
#define _IO_TIED_PUT_GET       0x0400      /* Put and get pointer logic tied. */
#define _IO_CURRENTLY_PUTTING  0x0800
#define _IO_IS_APPENDING       0x1000
#define _IO_IS_FILEBUF         0x2000
#define _IO_BAD_SEEN           0x4000
#define _IO_USER_LOCK          0x8000
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
