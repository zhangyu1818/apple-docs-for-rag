

- Kernel
- Kernel Enumerations
-  stackshot_flags_t 

Enumeration

# stackshot_flags_t

macOS 11.0+

``` source
typedef enum stackshot_flags_t : uint64_t {
    ...
} stackshot_flags_t;
```

## Topics

### Constants

STACKSHOT_ACTIVE_KERNEL_THREADS_ONLY

STACKSHOT_ASID

STACKSHOT_COLLECT_DELTA_SNAPSHOT

STACKSHOT_COLLECT_SHAREDCACHE_LAYOUT

STACKSHOT_DISABLE_LATENCY_INFO

STACKSHOT_DO_COMPRESS

STACKSHOT_ENABLE_BT_FAULTING

STACKSHOT_ENABLE_UUID_FAULTING

STACKSHOT_EXCLAVES

STACKSHOT_FROM_PANIC

STACKSHOT_GET_BOOT_PROFILE

STACKSHOT_GET_DQ

STACKSHOT_GET_GLOBAL_MEM_STATS

STACKSHOT_INCLUDE_DRIVER_THREADS_IN_KERNEL

STACKSHOT_INSTRS_CYCLES

STACKSHOT_KCDATA_FORMAT

STACKSHOT_NO_IO_STATS

STACKSHOT_PAGE_TABLES

STACKSHOT_RETRIEVE_EXISTING_BUFFER

STACKSHOT_SAVE_DYLD_COMPACTINFO

STACKSHOT_SAVE_IMP_DONATION_PIDS

STACKSHOT_SAVE_IN_KERNEL_BUFFER

STACKSHOT_SAVE_JETSAM_COALITIONS

STACKSHOT_SAVE_KEXT_LOADINFO

STACKSHOT_SAVE_LOADINFO

STACKSHOT_SKIP_EXCLAVES

STACKSHOT_THREAD_GROUP

STACKSHOT_THREAD_WAITINFO

STACKSHOT_TRYLOCK

