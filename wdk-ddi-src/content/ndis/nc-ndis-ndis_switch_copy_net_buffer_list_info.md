---
UID: NC:ndis.NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO
title: NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The Hyper-V extensible switch extension calls the CopyNetBufferListInfo function to copy the out-of-band (OOB) forwarding context from a source packet's NET_BUFFER_LIST structure to a destination packet's NET_BUFFER_LIST structure.
old-location: netvista\CopyNetBufferListInfo.htm
old-project: netvista
ms.assetid: 5CC345FA-C3EF-4122-8E9C-6EA27B20DD5A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.CopyNetBufferListInfo, CopyNetBufferListInfo callback function [Network Drivers Starting with Windows Vista], CopyNetBufferListInfo, NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO, NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO, ndis/CopyNetBufferListInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Ndis.h
apiname: 
-	CopyNetBufferListInfo
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO callback


## -description



The Hyper-V extensible switch extension calls the <i>CopyNetBufferListInfo</i> function to copy the out-of-band (OOB) forwarding context from a source packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure to a destination packet's <b>NET_BUFFER_LIST</b> structure. This context includes the extensible switch source port and network adapter information. The extensible switch destination port information can also be copied.




## -prototype


````
NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO CopyNetBufferListInfo;

NDIS_STATUS CopyNetBufferListInfo(
  _In_    NDIS_SWITCH_CONTEXT NdisSwitchContext,
  _Inout_ PNET_BUFFER_LIST    DestNetBufferList,
  _In_    PNET_BUFFER_LIST    SrcNetBufferList,
  _In_    UINT32              Flags
)
{ ... }
````


## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param DestNetBufferList [in, out]

A pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for the destination packet to which the extensible switch forwarding context is copied.  


### -param SrcNetBufferList [in]

A pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for the source packet from which the extensible switch forwarding context is copied. 


### -param Flags [in]

A UINT32 value. When the NDIS_SWITCH_COPY_NBL_INFO_FLAGS_PRESERVE_DESTINATIONS flag is specified, the function copies the extensible switch destination ports from the source packet to the destination packet.

The data that is contained within the source packet's <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a> union is always copied to the extensible switch forwarding context in the destination packet. This data includes the source port identifiers and index of the network adapter connection from which the packet originated. Depending on the number of extensible switch destination ports that are copied to the destination packet, the NumAvailableDestinations member of the <b>NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</b> union is updated in the destination packet.

For more information about the forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.


## -returns


If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.





## -remarks


The extensible switch extension calls the <i>CopyNetBufferListInfo</i> function to copy the OOB data from a source packet to a destination packet. This data includes the following:
<ul>
<li>
The data from the <b>NetBufferListInfo</b> array of the source packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

</li>
<li>
The <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a> data from the source packet's extensible switch forwarding context.

</li>
<li>
The data for the extensible switch destination ports from the source packet's extensible switch forwarding context.

<div class="alert"><b>Note</b>  This data is only copied if the NDIS_SWITCH_COPY_NBL_INFO_FLAGS_PRESERVE_DESTINATIONS flag is specified.</div>
<div> </div>
</li>
</ul>Before the extension calls <i>CopyNetBufferListInfo</i>, it must prepare the destination packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure by following these steps:
<ol>
<li>
The extension must first initialize a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for the destination packet that is derived from the source packet's  <b>NET_BUFFER_LIST</b> structure. 

For example, the extension can call <a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">NdisAllocateCloneNetBufferList</a> to create a complete copy of the source packet. The extension can also call <a href="..\ndis\nf-ndis-ndisallocatefragmentnetbufferlist.md">NdisAllocateFragmentNetBufferList</a> to create a copy of only a fragment of the source packet. For more information, see <a href="https://msdn.microsoft.com/6660aef5-ba67-4f15-98b6-547fa753bc76">Derived NET_BUFFER_LIST Structures</a>.

</li>
<li>The extension must call the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>  function to allocate the extensible switch forwarding context for the destination packet. This data is used to store the OOB extensible switch forwarding information, such as a packet's source and destination ports.</li>
</ol><div class="alert"><b>Note</b>  If the extension is creating or cloning the source packet, the extension must have previously called the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function for the packet. Source packets that the extension filters through the extensible switch driver stack already contain an allocated extensible switch forwarding context.</div><div> </div>


## -see-also

<a href="..\ndis\nf-ndis-ndisallocatefragmentnetbufferlist.md">NdisAllocateFragmentNetBufferList</a>

<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>

<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a>

<a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">NdisAllocateCloneNetBufferList</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

