---
UID: NF:ndischimney.NdisInvalidateOffload
title: NdisInvalidateOffload function
author: windows-driver-content
description: A protocol or intermediate driver calls the NdisInvalidateOffload function to invalidate previously offloaded TCP chimney state objects.
old-location: netvista\ndisinvalidateoffload.htm
old-project: netvista
ms.assetid: d9cb2724-cf14-4814-8a19-1237e0862b1a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisInvalidateOffload, ndischimney/NdisInvalidateOffload, netvista.ndisinvalidateoffload, NdisInvalidateOffload function [Network Drivers Starting with Windows Vista], tcp_chim_ndis_func_f9049fdc-87ff-467c-9427-d42876e16aa3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	ndis.lib
-	ndis.dll
apiname: 
-	NdisInvalidateOffload
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisInvalidateOffload function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisInvalidateOffload</b> function to invalidate previously offloaded TCP chimney state objects.


## -syntax


````
VOID NdisInvalidateOffload(
  _In_ NDIS_HANDLE                       NdisBindingHandle,
  _In_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param OffloadBlockList [in]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state objects that are being
     invalidated.


## -returns


None



## -remarks


An intermediate driver calls the 
    <b>NdisInvalidateOffload</b> function to propagate an invalidate offload operation that was initiated by
    the host stack. For more information, see 
    <mshelp:link keywords="netvista.propagating_state_manipulation_operations" tabindex="0">Propagating
    State-Manipulation Operations</mshelp:link>.

From the 
    <mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure that was passed to its 
    <mshelp:link keywords="netvista.miniportinvalidateoffload" tabindex="0"><i>
    MiniportInvalidateOffload</i></mshelp:link> function, the intermediate driver constructs an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see 
    <mshelp:link keywords="netvista.reusing_an_ndis_miniport_offload_block_list_structure" tabindex="0">Reusing an
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST Structure</mshelp:link>. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisInvalidateOffload</b> function.



## -see-also

<a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">MiniportInvalidateOffload</a>

<mshelp:link keywords="netvista.ndisminvalidateoffloadcomplete" tabindex="0"><b>
   NdisMInvalidateOffloadComplete</b></mshelp:link>

<mshelp:link keywords="netvista.protocolinvalidateoffloadcomplete" tabindex="0"><i>
   ProtocolInvalidateOffloadComplete</i></mshelp:link>

<mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInvalidateOffload function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

