---
UID: NS:ntddk._WHEA_PROCESSOR_GENERIC_ERROR_SECTION
title: _WHEA_PROCESSOR_GENERIC_ERROR_SECTION
author: windows-driver-content
description: Describes processor error data that is not specific to a particular processor architecture.
old-location: whea\whea_processor_generic_error_section.htm
old-project: whea
ms.assetid: d1ac2ca0-ad08-4149-b489-53807f308fc0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION, WHEA_GENERIC_PROCESSOR_ERROR, GENPROC_PROCERRTYPE_BUS, GENPROC_PROCERRTYPE_MAE, GENPROC_PROCISA_IPF, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION, WHEA_PROCESSOR_GENERIC_ERROR_SECTION, WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure [WHEA Drivers and Applications], GENPROC_OP_INSTRUCTIONEXE, *PWHEA_GENERIC_PROCESSOR_ERROR, GENPROC_FLAGS_PRECISEIP, GENPROC_PROCERRTYPE_UNKNOWN, GENPROC_PROCERRTYPE_CACHE, GENPROC_OP_DATAREAD, GENPROC_PROCISA_X86, GENPROC_FLAGS_RESTARTABLE, GENPROC_PROCISA_X64, GENPROC_FLAGS_CORRECTED, ntddk/WHEA_PROCESSOR_GENERIC_ERROR_SECTION, GENPROC_FLAGS_OVERFLOW, ntddk/PWHEA_PROCESSOR_GENERIC_ERROR_SECTION, GENPROC_PROCTYPE_IPF, _WHEA_PROCESSOR_GENERIC_ERROR_SECTION, whea.whea_processor_generic_error_section, whearef_589ac6c8-3889-4033-8776-0d8f402d1f69.xml, GENPROC_PROCTYPE_XPF, GENPROC_OP_DATAWRITE, GENPROC_PROCERRTYPE_TLB, GENPROC_OP_GENERIC, PWHEA_PROCESSOR_GENERIC_ERROR_SECTION structure pointer [WHEA Drivers and Applications]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntddk.h
apiname: 
-	WHEA_PROCESSOR_GENERIC_ERROR_SECTION
product: Windows
targetos: Windows
req.typenames: *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION, WHEA_PROCESSOR_GENERIC_ERROR_SECTION
---

# _WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure


## -description


The 
   <b>WHEA_PROCESSOR_GENERIC_ERROR_SECTION</b> 
   structure describes processor error data that is not specific to a particular processor architecture.


## -syntax


````
typedef struct _WHEA_PROCESSOR_GENERIC_ERROR_SECTION {
  WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS ValidBits;
  UCHAR                                          ProcessorType;
  UCHAR                                          InstructionSet;
  UCHAR                                          ErrorType;
  UCHAR                                          Operation;
  UCHAR                                          Flags;
  UCHAR                                          Level;
  USHORT                                         Reserved;
  ULONGLONG                                      CPUVersion;
  UCHAR                                          CPUBrandString[128];
  ULONGLONG                                      ProcessorId;
  ULONGLONG                                      TargetAddress;
  ULONGLONG                                      RequesterId;
  ULONGLONG                                      ResponderId;
  ULONGLONG                                      InstructionPointer;
} WHEA_PROCESSOR_GENERIC_ERROR_SECTION, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION;
````


## -struct-fields




### -field ValidBits

A 
      <a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section_validbits.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS</a> 
      union that specifies which members of this structure contain valid data.


### -field ProcessorType

The processor architecture of the processor.

This member contains valid data only if the 
       <b>ProcessorType</b> bit of the <b>ValidBits</b> member is set.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCTYPE_XPF"></a><a id="genproc_proctype_xpf"></a><dl>
<dt><b>GENPROC_PROCTYPE_XPF</b></dt>
</dl>
</td>
<td width="60%">
x86/x64 processor family

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCTYPE_IPF"></a><a id="genproc_proctype_ipf"></a><dl>
<dt><b>GENPROC_PROCTYPE_IPF</b></dt>
</dl>
</td>
<td width="60%">
Intel Itanium processor family

</td>
</tr>
</table> 


### -field InstructionSet

The instruction set that was executing when the error occurred.

This member contains valid data only if the <b>InstructionSet</b> bit of the 
       <b>ValidBits</b> member is set.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCISA_X86"></a><a id="genproc_procisa_x86"></a><dl>
<dt><b>GENPROC_PROCISA_X86</b></dt>
</dl>
</td>
<td width="60%">
x86

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCISA_IPF"></a><a id="genproc_procisa_ipf"></a><dl>
<dt><b>GENPROC_PROCISA_IPF</b></dt>
</dl>
</td>
<td width="60%">
Itanium

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCISA_X64"></a><a id="genproc_procisa_x64"></a><dl>
<dt><b>GENPROC_PROCISA_X64</b></dt>
</dl>
</td>
<td width="60%">
x64

</td>
</tr>
</table> 


### -field ErrorType

The type of error that occurred.

This member contains valid data only if the <b>ErrorType</b> bit of the 
       <b>ValidBits</b> member is set.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCERRTYPE_UNKNOWN"></a><a id="genproc_procerrtype_unknown"></a><dl>
<dt><b>GENPROC_PROCERRTYPE_UNKNOWN</b></dt>
</dl>
</td>
<td width="60%">
Unknown error

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCERRTYPE_CACHE"></a><a id="genproc_procerrtype_cache"></a><dl>
<dt><b>GENPROC_PROCERRTYPE_CACHE</b></dt>
</dl>
</td>
<td width="60%">
Cache error

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCERRTYPE_TLB"></a><a id="genproc_procerrtype_tlb"></a><dl>
<dt><b>GENPROC_PROCERRTYPE_TLB</b></dt>
</dl>
</td>
<td width="60%">
Translation lookaside buffer error

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCERRTYPE_BUS"></a><a id="genproc_procerrtype_bus"></a><dl>
<dt><b>GENPROC_PROCERRTYPE_BUS</b></dt>
</dl>
</td>
<td width="60%">
Bus error

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_PROCERRTYPE_MAE"></a><a id="genproc_procerrtype_mae"></a><dl>
<dt><b>GENPROC_PROCERRTYPE_MAE</b></dt>
</dl>
</td>
<td width="60%">
Microarchitecture error

</td>
</tr>
</table> 


### -field Operation

The type of operation that was executing when the error occurred.

This member contains valid data only if the <b>Operation</b> bit of the 
       <b>ValidBits</b> member is set.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="GENPROC_OP_GENERIC"></a><a id="genproc_op_generic"></a><dl>
<dt><b>GENPROC_OP_GENERIC</b></dt>
</dl>
</td>
<td width="60%">
Unknown or generic operation

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_OP_DATAREAD"></a><a id="genproc_op_dataread"></a><dl>
<dt><b>GENPROC_OP_DATAREAD</b></dt>
</dl>
</td>
<td width="60%">
Data read

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_OP_DATAWRITE"></a><a id="genproc_op_datawrite"></a><dl>
<dt><b>GENPROC_OP_DATAWRITE</b></dt>
</dl>
</td>
<td width="60%">
Data write

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_OP_INSTRUCTIONEXE"></a><a id="genproc_op_instructionexe"></a><dl>
<dt><b>GENPROC_OP_INSTRUCTIONEXE</b></dt>
</dl>
</td>
<td width="60%">
Instruction execution

</td>
</tr>
</table> 


### -field Flags

A bit-wise OR'ed combination of flags that provides additional information about the error.

This member contains valid data only if the <b>Flags</b> bit of the 
       <b>ValidBits</b> member is set.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="GENPROC_FLAGS_RESTARTABLE"></a><a id="genproc_flags_restartable"></a><dl>
<dt><b>GENPROC_FLAGS_RESTARTABLE</b></dt>
</dl>
</td>
<td width="60%">
Program execution can be restarted reliably after the error.

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_FLAGS_PRECISEIP"></a><a id="genproc_flags_preciseip"></a><dl>
<dt><b>GENPROC_FLAGS_PRECISEIP</b></dt>
</dl>
</td>
<td width="60%">
The instruction pointer in the <b>InstructionPointer</b> member is directly 
        associated with the error.

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_FLAGS_OVERFLOW"></a><a id="genproc_flags_overflow"></a><dl>
<dt><b>GENPROC_FLAGS_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
A machine check overflow occurred. This happens when a second error occurs while the results of the 
        previous error are still in the error reporting resources.

</td>
</tr>
<tr>
<td width="40%"><a id="GENPROC_FLAGS_CORRECTED"></a><a id="genproc_flags_corrected"></a><dl>
<dt><b>GENPROC_FLAGS_CORRECTED</b></dt>
</dl>
</td>
<td width="60%">
The error was corrected by the hardware or the firmware.

</td>
</tr>
</table> 


### -field Level

The level of the structure where the error occurred, with zero being the lowest level of cache.

This member contains valid data only if the <b>Level</b> bit of the 
       <b>ValidBits</b> member is set.


### -field Reserved

Reserved for system use.


### -field CPUVersion

The CPU version, which includes the family, model, and stepping information.
<ul>
<li>For x86 and x64 processors, this member contains a 
        <a href="..\ntddk\ns-ntddk-_whea_processor_family_info.md">WHEA_PROCESSOR_FAMILY_INFO</a> union.</li>
<li>For Itanium processors, this member contains the data provided in CPUID Register 3.</li>
</ul>This member contains valid data only if the <b>CPUVersion</b> bit of the 
       <b>ValidBits</b> member is set.


### -field CPUBrandString

The CPU brand string.
<ul>
<li>For x86 and x64 processors, this member contains the result of executing the CPUID instruction with EAX 
        set to 0x80000002 on input, followed by executing the CPUID instruction with EAX set to 0x80000003 on input. 
        For more information about the CPUID instruction, see the 
        <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.</li>
<li>For Itanium processors, this member contains the result of executing the 
        <b>PAL_BRAND_INFO</b> procedure.</li>
</ul>This member contains valid data only if the <b>CpuBrandString</b> bit of the 
       <b>ValidBits</b> member is set.


### -field ProcessorId

An identifier that uniquely identifies the logical processor in the system.
<ul>
<li>For x86 and x64 processors, this member contains the value programmed into the local APIC ID 
        register.</li>
<li>For Itanium processors, this member contains the value programmed into the LID register.</li>
</ul>This member contains valid data only if the <b>ProcessorId</b> bit of the 
       <b>ValidBits</b> member is set.


### -field TargetAddress

The target address associated with the error.

This member contains valid data only if the <b>TargetAddress</b> bit of the 
       <b>ValidBits</b> member is set.


### -field RequesterId

An identifier that uniquely identifies the requester associated with the error.

This member contains valid data only if the <b>RequesterId</b> bit of the 
       <b>ValidBits</b> member is set.


### -field ResponderId

An identifier that uniquely identifies the responder associated with the error.

This member contains valid data only if the <b>ResponderId</b> bit of the 
       <b>ValidBits</b> member is set.


### -field InstructionPointer

The instruction pointer at the time that the error occurred.

This member contains valid data only if the <b>InstructionPointer</b> bit of the 
       <b>ValidBits</b> member is set.


## -remarks


The 
     <b>WHEA_PROCESSOR_GENERIC_ERROR_SECTION</b> 
     structure describes the error data that is contained in a generic processor error section of an 
     <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a generic processor 
     error section only if the <b>SectionType</b> member of one of the 
     <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> 
     structures that describe the error record sections for that error record contains 
     <b>PROCESSOR_GENERIC_ERROR_SECTION_GUID</b>.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_processor_family_info.md">WHEA_PROCESSOR_FAMILY_INFO</a>

<a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section_validbits.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS</a>

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

