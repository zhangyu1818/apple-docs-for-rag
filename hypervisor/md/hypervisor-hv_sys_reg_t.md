

- Hypervisor
-  hv_sys_reg_t 

Structure

# hv_sys_reg_t

The type of system registers.

macOS

``` source
struct hv_sys_reg_t
```

## Topics

### Initializers

init(UInt16)

Creates a new system-register instance.

init(rawValue: UInt16)

Creates a new system-register instance.

### System registers

var HV_SYS_REG_ID_AA64DFR0_EL1: hv_sys_reg_t

The value that describes the AArch64 Debug Feature Register 0.

var HV_SYS_REG_ID_AA64DFR1_EL1: hv_sys_reg_t

The value that describes the AArch64 Debug Feature Register 1.

var HV_SYS_REG_ID_AA64ISAR0_EL1: hv_sys_reg_t

The value that describes the AArch64 Instruction Set Attribute Register 0.

var HV_SYS_REG_ID_AA64ISAR1_EL1: hv_sys_reg_t

The value that describes the AArch64 Instruction Set Attribute Register 1.

var HV_SYS_REG_ID_AA64MMFR0_EL1: hv_sys_reg_t

The value that describes the AArch64 Memory Model Feature Register 0.

var HV_SYS_REG_ID_AA64MMFR1_EL1: hv_sys_reg_t

The value that describes the AArch64 Memory Model Feature Register 1.

var HV_SYS_REG_ID_AA64MMFR2_EL1: hv_sys_reg_t

The value that describes the AArch64 Memory Model Feature Register 2.

var HV_SYS_REG_ID_AA64PFR0_EL1: hv_sys_reg_t

The value that describes the AArch64 Processor Feature Register 0.

var HV_SYS_REG_ID_AA64PFR1_EL1: hv_sys_reg_t

The value that describes the AArch64 Processor Feature Register 1.

var HV_SYS_REG_APDAKEYHI_EL1: hv_sys_reg_t

The value that represents the system register APDAKEYHI_EL1.

var HV_SYS_REG_APDAKEYLO_EL1: hv_sys_reg_t

The value that represents the system register APDAKEYLO_E1.

var HV_SYS_REG_APDBKEYHI_EL1: hv_sys_reg_t

The value that represents the system register ADPBKEYHI_EL1.

var HV_SYS_REG_APDBKEYLO_EL1: hv_sys_reg_t

The value that represents the system register APDBKEYLO_E1.

var HV_SYS_REG_APGAKEYHI_EL1: hv_sys_reg_t

The value that represents the system register AOGAKEYHI_EL1.

var HV_SYS_REG_APGAKEYLO_EL1: hv_sys_reg_t

The value that represents the system register APGAKEYLO_REL1.

var HV_SYS_REG_APIAKEYHI_EL1: hv_sys_reg_t

The value that represents the system register APIAKEYHI_EL1.

var HV_SYS_REG_APIAKEYLO_EL1: hv_sys_reg_t

The value that represents the system register APIAKEYLO_EL1.

var HV_SYS_REG_APIBKEYHI_EL1: hv_sys_reg_t

The value that represents the system register APIBKEYHI_EL1.

var HV_SYS_REG_APIBKEYLO_EL1: hv_sys_reg_t

The value that represents the system register APIBKEYLO_EL1.

var HV_SYS_REG_DBGBCR0_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR0_EL1.

var HV_SYS_REG_DBGBCR10_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR10_EL1.

var HV_SYS_REG_DBGBCR11_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR11_EL1.

var HV_SYS_REG_DBGBCR12_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR12_EL1.

var HV_SYS_REG_DBGBCR13_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR13_EL1.

var HV_SYS_REG_DBGBCR14_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR14_EL1.

var HV_SYS_REG_DBGBCR15_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR15_EL1.

var HV_SYS_REG_DBGBCR1_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR1_EL1.

var HV_SYS_REG_DBGBCR2_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR1_EL1.

var HV_SYS_REG_DBGBCR3_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR3_EL1.

var HV_SYS_REG_DBGBCR4_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR4_EL1.

var HV_SYS_REG_DBGBCR5_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR5_EL1.

var HV_SYS_REG_DBGBCR6_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR6_EL1.

var HV_SYS_REG_DBGBCR7_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR7_EL1.

var HV_SYS_REG_DBGBCR8_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR8_EL1.

var HV_SYS_REG_DBGBCR9_EL1: hv_sys_reg_t

The value that represents the system register DBGBCR9_EL1.

var HV_SYS_REG_DBGBVR0_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR0_EL1.

var HV_SYS_REG_DBGBVR10_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR10_EL1.

var HV_SYS_REG_DBGBVR11_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR11_EL1.

var HV_SYS_REG_DBGBVR12_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR12_EL1.

var HV_SYS_REG_DBGBVR13_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR13_EL1.

var HV_SYS_REG_DBGBVR14_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR14_EL1.

var HV_SYS_REG_DBGBVR15_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR15_EL1.

var HV_SYS_REG_DBGBVR1_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR1_EL1.

var HV_SYS_REG_DBGBVR2_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR2_EL1.

var HV_SYS_REG_DBGBVR3_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR3_EL1.

var HV_SYS_REG_DBGBVR4_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR4_EL1.

var HV_SYS_REG_DBGBVR5_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR5_EL1.

var HV_SYS_REG_DBGBVR6_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR6_EL1.

var HV_SYS_REG_DBGBVR7_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR7_EL1.

var HV_SYS_REG_DBGBVR8_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR8_EL1.

var HV_SYS_REG_DBGBVR9_EL1: hv_sys_reg_t

The value that represents the system register DBGBVR9_EL1.

var HV_SYS_REG_DBGWCR0_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR0_EL1.

var HV_SYS_REG_DBGWCR10_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR10_EL1.

var HV_SYS_REG_DBGWCR11_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR11_EL1.

var HV_SYS_REG_DBGWCR12_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR12_EL1.

var HV_SYS_REG_DBGWCR13_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR13_EL1.

var HV_SYS_REG_DBGWCR14_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR14_EL1.

var HV_SYS_REG_DBGWCR15_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR15_EL1.

var HV_SYS_REG_DBGWCR1_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR1_EL1.

var HV_SYS_REG_DBGWCR2_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR2_EL1.

var HV_SYS_REG_DBGWCR3_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR3_EL1.

var HV_SYS_REG_DBGWCR4_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR4_EL1.

var HV_SYS_REG_DBGWCR5_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR5_EL1.

var HV_SYS_REG_DBGWCR6_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR6_EL1.

var HV_SYS_REG_DBGWCR7_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR7_EL1.

var HV_SYS_REG_DBGWCR8_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR8_EL1.

var HV_SYS_REG_DBGWCR9_EL1: hv_sys_reg_t

The value that represents the system register DBGWCR9_EL1.

var HV_SYS_REG_DBGWVR0_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR0_EL1.

var HV_SYS_REG_DBGWVR10_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR10_EL1.

var HV_SYS_REG_DBGWVR11_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR11_EL1.

var HV_SYS_REG_DBGWVR12_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR12_EL1.

var HV_SYS_REG_DBGWVR13_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR13_EL1.

var HV_SYS_REG_DBGWVR14_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR14_EL1.

var HV_SYS_REG_DBGWVR15_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR15_EL1.

var HV_SYS_REG_DBGWVR1_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR1_EL1.

var HV_SYS_REG_DBGWVR2_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR2_EL1.

var HV_SYS_REG_DBGWVR3_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR3_EL1.

var HV_SYS_REG_DBGWVR4_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR4_EL1.

var HV_SYS_REG_DBGWVR5_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR5_EL1.

var HV_SYS_REG_DBGWVR6_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR6_EL1.

var HV_SYS_REG_DBGWVR7_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR7_EL1.

var HV_SYS_REG_DBGWVR8_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR8_EL1.

var HV_SYS_REG_DBGWVR9_EL1: hv_sys_reg_t

The value that represents the system register DBGWVR9_EL1.

var HV_SYS_REG_MDCCINT_EL1: hv_sys_reg_t

The value that represents the system register MDCCINT_EL1.

var HV_SYS_REG_AFSR0_EL1: hv_sys_reg_t

The value that represents the system register AFSR0_EL1.

var HV_SYS_REG_AFSR1_EL1: hv_sys_reg_t

The value that represents the system register AFSR1_EL1.

var HV_SYS_REG_AMAIR_EL1: hv_sys_reg_t

The value that represents the system register AMAIR_EL1.

var HV_SYS_REG_CNTKCTL_EL1: hv_sys_reg_t

The value that represents the system register CNTKCTL_EL1.

var HV_SYS_REG_CNTV_CVAL_EL0: hv_sys_reg_t

The value that represents the system register CNTV_CVAL_EL0.

var HV_SYS_REG_CONTEXTIDR_EL1: hv_sys_reg_t

The value that represents the system register CONTEXTIDR_EL1.

var HV_SYS_REG_CPACR_EL1: hv_sys_reg_t

The value that represents the system register CPACR_EL1.

var HV_SYS_REG_CSSELR_EL1: hv_sys_reg_t

The value that represents the system register CSSELR_EL1.

var HV_SYS_REG_ELR_EL1: hv_sys_reg_t

The value that represents the system register ELR_EL1.

var HV_SYS_REG_ESR_EL1: hv_sys_reg_t

The value that represents the system register ESR_EL1.

var HV_SYS_REG_FAR_EL1: hv_sys_reg_t

The value that represents the system register FAR_EL1.

var HV_SYS_REG_MAIR_EL1: hv_sys_reg_t

The value that represents the system register MAIR_EL1.

var HV_SYS_REG_MDSCR_EL1: hv_sys_reg_t

The value that represents the system register MDSCR_EL0.

var HV_SYS_REG_MIDR_EL1: hv_sys_reg_t

The value that represents the system register MIDR_EL1.

var HV_SYS_REG_MPIDR_EL1: hv_sys_reg_t

The value that represents the system register MPIDR_EL1.

var HV_SYS_REG_CNTV_CTL_EL0: hv_sys_reg_t

The value that represents the system register CNTV_CRTL_EL0.

var HV_SYS_REG_PAR_EL1: hv_sys_reg_t

The value that represents the system register PAR_EL1.

var HV_SYS_REG_SCTLR_EL1: hv_sys_reg_t

The value that represents the system register SCTLR_EL1.

var HV_SYS_REG_SPSR_EL1: hv_sys_reg_t

The value that represents the system register SPSR_EL1.

var HV_SYS_REG_SP_EL0: hv_sys_reg_t

The value that represents the system register SP_EL0.

var HV_SYS_REG_SP_EL1: hv_sys_reg_t

The value that represents the system register SP_EL1.

var HV_SYS_REG_TCR_EL1: hv_sys_reg_t

The value that represents the system register TCR_EL1.

var HV_SYS_REG_TPIDRRO_EL0: hv_sys_reg_t

The value that represents the system register TPIDRRO_EL0.

var HV_SYS_REG_TPIDR_EL0: hv_sys_reg_t

The value that represents the system register TPIDR_EL0.

var HV_SYS_REG_TPIDR_EL1: hv_sys_reg_t

The value that represents the system register TPIDR_EL1.

var HV_SYS_REG_TTBR0_EL1: hv_sys_reg_t

The value that represents the system register TTBR0_EL1.

var HV_SYS_REG_TTBR1_EL1: hv_sys_reg_t

The value that represents the system register TTBR1_EL1.

var HV_SYS_REG_VBAR_EL1: hv_sys_reg_t

The value that represents the system register VBAR_EL1.

var HV_CACHE_TYPE_DATA: hv_cache_type_t

The value that describes a cached data value.

var HV_CACHE_TYPE_INSTRUCTION: hv_cache_type_t

The value that describes a cached instuction value.

var HV_FEATURE_REG_CLIDR_EL1: hv_feature_reg_t

The value that describes Cache Level ID Register, EL1.

var HV_FEATURE_REG_CTR_EL0: hv_feature_reg_t

The value that describes Cache Type Register, EL0.

var HV_FEATURE_REG_DCZID_EL0: hv_feature_reg_t

The value that describes Data Cache Zero ID Register, EL0.

var HV_SYS_REG_CNTHCTL_EL2: hv_sys_reg_t

var HV_SYS_REG_CNTHP_CTL_EL2: hv_sys_reg_t

var HV_SYS_REG_CNTHP_CVAL_EL2: hv_sys_reg_t

var HV_SYS_REG_CNTHP_TVAL_EL2: hv_sys_reg_t

var HV_SYS_REG_CNTP_CTL_EL0: hv_sys_reg_t

var HV_SYS_REG_CNTP_CVAL_EL0: hv_sys_reg_t

var HV_SYS_REG_CNTP_TVAL_EL0: hv_sys_reg_t

var HV_SYS_REG_CNTVOFF_EL2: hv_sys_reg_t

var HV_SYS_REG_CPTR_EL2: hv_sys_reg_t

var HV_SYS_REG_ELR_EL2: hv_sys_reg_t

var HV_SYS_REG_ESR_EL2: hv_sys_reg_t

var HV_SYS_REG_FAR_EL2: hv_sys_reg_t

var HV_SYS_REG_HCR_EL2: hv_sys_reg_t

var HV_SYS_REG_HPFAR_EL2: hv_sys_reg_t

var HV_SYS_REG_ID_AA64SMFR0_EL1: hv_sys_reg_t

var HV_SYS_REG_ID_AA64ZFR0_EL1: hv_sys_reg_t

var HV_SYS_REG_MAIR_EL2: hv_sys_reg_t

var HV_SYS_REG_MDCR_EL2: hv_sys_reg_t

var HV_SYS_REG_SCTLR_EL2: hv_sys_reg_t

var HV_SYS_REG_SCXTNUM_EL0: hv_sys_reg_t

var HV_SYS_REG_SCXTNUM_EL1: hv_sys_reg_t

var HV_SYS_REG_SMCR_EL1: hv_sys_reg_t

var HV_SYS_REG_SMPRI_EL1: hv_sys_reg_t

var HV_SYS_REG_SPSR_EL2: hv_sys_reg_t

var HV_SYS_REG_SP_EL2: hv_sys_reg_t

var HV_SYS_REG_TCR_EL2: hv_sys_reg_t

var HV_SYS_REG_TPIDR2_EL0: hv_sys_reg_t

var HV_SYS_REG_TPIDR_EL2: hv_sys_reg_t

var HV_SYS_REG_TTBR0_EL2: hv_sys_reg_t

var HV_SYS_REG_TTBR1_EL2: hv_sys_reg_t

var HV_SYS_REG_VBAR_EL2: hv_sys_reg_t

var HV_SYS_REG_VMPIDR_EL2: hv_sys_reg_t

var HV_SYS_REG_VPIDR_EL2: hv_sys_reg_t

var HV_SYS_REG_VTCR_EL2: hv_sys_reg_t

var HV_SYS_REG_VTTBR_EL2: hv_sys_reg_t

var HV_SYS_REG_ACTLR_EL1: hv_sys_reg_t

### Instance properties

var rawValue: UInt16

An unsigned 16-bit integer that represents the system registers.

## Relationships

### Conforms To

- BitwiseCopyable
- Equatable
- Hashable
- RawRepresentable
- Sendable

## See Also

### System registers

func hv_vcpu_get_sys_reg(hv_vcpu_t, hv_sys_reg_t, UnsafeMutablePointer&lt;UInt64>) -> hv_return_t

Gets the current value of a vCPU system register.

func hv_vcpu_set_sys_reg(hv_vcpu_t, hv_sys_reg_t, UInt64) -> hv_return_t

Sets the value of a vCPU system register.

