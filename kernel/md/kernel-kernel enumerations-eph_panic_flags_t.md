

- Kernel
- Kernel Enumerations
-  eph_panic_flags_t 

Enumeration

# eph_panic_flags_t

macOS 13.0+

``` source
typedef enum eph_panic_flags_t : uint64_t {
    ...
} eph_panic_flags_t;
```

## Topics

### Constants

EMBEDDED_PANIC_HEADER_FLAG_BUTTON_RESET_PANIC

EMBEDDED_PANIC_HEADER_FLAG_COMPANION_PROC_INITIATED_PANIC

EMBEDDED_PANIC_HEADER_FLAG_COMPRESS_FAILED

EMBEDDED_PANIC_HEADER_FLAG_COREDUMP_COMPLETE

EMBEDDED_PANIC_HEADER_FLAG_COREDUMP_FAILED

EMBEDDED_PANIC_HEADER_FLAG_COREFILE_UNLINKED

EMBEDDED_PANIC_HEADER_FLAG_ENCRYPTED_COREDUMP_SKIPPED

EMBEDDED_PANIC_HEADER_FLAG_EXCLAVE_PANIC

EMBEDDED_PANIC_HEADER_FLAG_INCOHERENT_PANICLOG

EMBEDDED_PANIC_HEADER_FLAG_INTEGRATED_COPROC_INITIATED_PANIC

EMBEDDED_PANIC_HEADER_FLAG_KERNEL_COREDUMP_SKIPPED_EXCLUDE_REGIONS_UNAVAILABLE

EMBEDDED_PANIC_HEADER_FLAG_NESTED_PANIC

EMBEDDED_PANIC_HEADER_FLAG_STACKSHOT_DATA_COMPRESSED

EMBEDDED_PANIC_HEADER_FLAG_STACKSHOT_FAILED_DEBUGGERSYNC

EMBEDDED_PANIC_HEADER_FLAG_STACKSHOT_FAILED_ERROR

EMBEDDED_PANIC_HEADER_FLAG_STACKSHOT_FAILED_INCOMPLETE

EMBEDDED_PANIC_HEADER_FLAG_STACKSHOT_FAILED_NESTED

EMBEDDED_PANIC_HEADER_FLAG_STACKSHOT_SUCCEEDED

EMBEDDED_PANIC_HEADER_FLAG_USERSPACE_INITIATED_PANIC

