---
UID: NS:ntddndis._NDIS_HD_SPLIT_PARAMETERS
title: _NDIS_HD_SPLIT_PARAMETERS
author: windows-driver-content
description: The NDIS_HD_SPLIT_PARAMETERS structure defines the current header-data split settings of a miniport adapter.
old-location: netvista\ndis_hd_split_parameters.htm
old-project: netvista
ms.assetid: 1cc76765-871e-4cd0-b927-b0b4d3d746b4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_hd_split_parameters, NDIS_HD_SPLIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_HD_SPLIT_PARAMETERS, ntddndis/NDIS_HD_SPLIT_PARAMETERS, NDIS_HD_SPLIT_PARAMETERS, header_data_split_ref_f7f3a3c4-4259-44a5-abce-fa393922f97d.xml, _NDIS_HD_SPLIT_PARAMETERS, *PNDIS_HD_SPLIT_PARAMETERS, PNDIS_HD_SPLIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], PNDIS_HD_SPLIT_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
-	ntddndis.h
apiname: 
-	NDIS_HD_SPLIT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: *PNDIS_HD_SPLIT_PARAMETERS, NDIS_HD_SPLIT_PARAMETERS
---

# _NDIS_HD_SPLIT_PARAMETERS structure


## -description


The NDIS_HD_SPLIT_PARAMETERS structure defines the current header-data split settings of a miniport
  adapter.


## -syntax


````
typedef struct _NDIS_HD_SPLIT_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              HDSplitCombineFlags;
} NDIS_HD_SPLIT_PARAMETERS, *PNDIS_HD_SPLIT_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     provider characteristics structure (NDIS_HD_SPLIT_PARAMETERS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_ HD_SPLIT_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_HD_SPLIT_PARAMETERS_REVISION_1.


### -field HDSplitCombineFlags

A set of flags that specify the current header-data split settings of a miniport adapter. A
     protocol driver or user-mode application can specify a bitwise OR of the following flags:
     




##### - HDSplitCombineFlags.NDIS_HD_SPLIT_COMBINE_ALL_HEADERS

The miniport adapter should combine split frames. If header-data split is enabled in the
       hardware, the miniport driver should combine the header and data before indicating the frame to
       NDIS.


## -remarks


The NDIS_HD_SPLIT_PARAMETERS structure is used in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569587">OID_GEN_HD_SPLIT_PARAMETERS</a> OID set
    request to specify the current header-data split settings of a miniport adapter.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569587">OID_GEN_HD_SPLIT_PARAMETERS</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_HD_SPLIT_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

