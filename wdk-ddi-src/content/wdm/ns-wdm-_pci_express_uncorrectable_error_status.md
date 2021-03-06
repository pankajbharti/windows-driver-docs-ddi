---
UID: NS:wdm._PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
title: _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
author: windows-driver-content
description: The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) uncorrectable error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_uncorrectable_error_status.htm
old-project: PCI
ms.assetid: 9d7dcdee-052a-4082-a337-be3a35c5eef9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PCI.pci_express_uncorrectable_error_status, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union pointer [Buses], pci_struct_9341a010-06c8-46ee-931f-2a67756c12d2.xml, PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wdm.h
apiname: 
-	PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure


## -description


The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) uncorrectable error status register of a PCIe advanced error reporting capability structure.


## -syntax


````
typedef union _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS {
  struct {
    ULONG Undefined  :1;
    ULONG Reserved1  :3;
    ULONG DataLinkProtocolError  :1;
    ULONG SurpriseDownError  :1;
    ULONG Reserved2  :6;
    ULONG PoisonedTLP  :1;
    ULONG FlowControlProtocolError  :1;
    ULONG CompletionTimeout  :1;
    ULONG CompleterAbort  :1;
    ULONG UnexpectedCompletion  :1;
    ULONG ReceiverOverflow  :1;
    ULONG MalformedTLP  :1;
    ULONG ECRCError  :1;
    ULONG UnsupportedRequestError  :1;
    ULONG Reserved3  :11;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.Undefined

 


### -field DUMMYSTRUCTNAME.Reserved1

 


### -field DUMMYSTRUCTNAME.DataLinkProtocolError

 


### -field DUMMYSTRUCTNAME.SurpriseDownError

 


### -field DUMMYSTRUCTNAME.Reserved2

 


### -field DUMMYSTRUCTNAME.PoisonedTLP

 


### -field DUMMYSTRUCTNAME.FlowControlProtocolError

 


### -field DUMMYSTRUCTNAME.CompletionTimeout

 


### -field DUMMYSTRUCTNAME.CompleterAbort

 


### -field DUMMYSTRUCTNAME.UnexpectedCompletion

 


### -field DUMMYSTRUCTNAME.ReceiverOverflow

 


### -field DUMMYSTRUCTNAME.MalformedTLP

 


### -field DUMMYSTRUCTNAME.ECRCError

 


### -field DUMMYSTRUCTNAME.UnsupportedRequestError

 


### -field DUMMYSTRUCTNAME.AcsViolation

 


### -field DUMMYSTRUCTNAME.UncorrectableInternalError

 


### -field DUMMYSTRUCTNAME.MCBlockedTlp

 


### -field DUMMYSTRUCTNAME.AtomicOpEgressBlocked

 


### -field DUMMYSTRUCTNAME.TlpPrefixBlocked

 


### -field DUMMYSTRUCTNAME.Reserved3

 


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure.


#### - Reserved2

Reserved.


#### - SurpriseDownError

A single bit that indicates that a surprise down error has occurred.


#### - DataLinkProtocolError

A single bit that indicates that a data link protocol error has occurred.


#### - UnsupportedRequestError

A single bit that indicates that an unsupported request error has occurred.


#### - MalformedTLP

A single bit that indicates that a malformed transaction layer packet (TLP) has been detected.


#### - CompleterAbort

A single bit that indicates that a completer abort has occurred.


#### - FlowControlProtocolError

A single bit that indicates that a flow control protocol error has occurred.


#### - Undefined

A single bit that contains an undefined value. In versions of the <i>PCIe Specification</i> prior to version 1.1, this bit indicates that a link training error has occurred.


#### - CompletionTimeout

A single bit that indicates that a completion timeout has occurred.


#### - ECRCError

A single bit that indicates that an end-to-end cyclic redundancy check (ECRC) error has occurred.


#### - UnexpectedCompletion

A single bit that indicates that an unexpected completion has occurred.


#### - PoisonedTLP

A single bit that indicates that a poisoned transaction layer packet (TLP) has been detected.


#### - ReceiverOverflow

A single bit that indicates that the receiver has overflowed.


#### - Reserved1

Reserved.


#### - Reserved3

Reserved.


## -remarks


The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

