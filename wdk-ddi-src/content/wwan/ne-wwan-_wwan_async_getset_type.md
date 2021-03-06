---
UID: NE:wwan._WWAN_ASYNC_GETSET_TYPE
title: _WWAN_ASYNC_GETSET_TYPE
author: windows-driver-content
description: The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests.
old-location: netvista\wwan_async_getset_type.htm
old-project: netvista
ms.assetid: 2FECDA17-7B38-4636-AFAF-D923AECFAF68
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/WwanAsyncGetDeviceServices, wwan/WwanAsyncSmsDelete, WWAN_ASYNC_GETSET_TYPE_MAX, WwanAsyncGetDeviceServices, netvista.wwan_async_getset_type, WwanAsyncGetDeviceCaps, wwan/WwanAsyncGetSmsConfiguration, WwanAsyncSetDeviceServiceCommand, WwanAsyncGetVisibleProviders, wwan/WwanAsyncGetPacketService, *PWWAN_ASYNC_GETSET_TYPE, WwanAsyncGetConnect, WwanAsyncSetProvisionedContext, WwanAsyncGetPreferredProviders, WwanAsyncSetSignalState, wwan/WwanAsyncSetPinEx, wwan/WwanAsyncGetConnect, WwanAsyncSmsSend, WwanAsyncGetReadyInfo, WwanAsyncUssdRequest, wwan/WwanAsyncGetHomeProvider, WwanAsyncGetProvisionedContexts, wwan/WwanAsyncSetPin, _WWAN_ASYNC_GETSET_TYPE, wwan/WwanAsyncSmsSend, wwan/WwanAsyncGetProvisionedContexts, wwan/WwanAsyncSetProfileIndex, WwanAsyncSetPacketService, WWAN_ASYNC_GETSET_TYPE, wwan/WwanAsyncGetPinList, WwanAsyncSetConnect, WwanAsyncSmsRead, WwanAsyncSetProfileIndex, WwanAsyncSetRegisterState, wwan/WwanAsyncSetPacketService, wwan/WwanAsyncGetRegisterState, WwanAsyncSubscribeDeviceServiceEvents, wwan/WwanAsyncSetSmsConfiguration, WwanAsyncAuthChallenge, wwan/WwanAsyncGetDeviceServiceCommand get request., WwanAsyncGetPacketService, WwanAsyncSetPin, WwanAsyncGetSmsConfiguration, wwan/WwanAsyncSetRadioState, wwan/WwanAsyncSetConnect, WWAN_ASYNC_GETSET_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanAsyncGetRadioState, WwanAsyncGetHomeProvider, wwan/WwanAsyncUssdRequest, wwan/WwanAsyncGetPinEx get request., WwanAsyncSetPreferredProviders, wwan/WwanAsyncGetRadioState, WwanAsyncSmsStatus, wwan/WwanAsyncSetRegisterState, wwan/WwanAsyncSubscribeDeviceServiceEvents, WwanAsyncSmsDelete, wwan/WwanAsyncSetSignalState, wwan/WwanAsyncSetHomeProvider, wwan/WwanAsyncSetVendorSpecific, wwan/WwanAsyncSetProvisionedContext, WwanAsyncGetRegisterState, wwan/WwanAsyncGetDeviceCaps, wwan/WwanAsyncSetServiceActivation, WwanAsyncGetSignalState, WwanAsyncGetPin, WwanAsyncGetPinList, WwanAsyncGetDeviceServiceCommand get request., wwan/WwanAsyncGetPreferredProviders, wwan/WWAN_ASYNC_GETSET_TYPE_MAX, WwanAsyncSetPinEx, WwanAsyncGetPinEx get request., WwanAsyncSetVendorSpecific, wwan/WwanAsyncSmsStatus, wwan/WwanAsyncSetPreferredProviders, WwanAsyncSetRadioState, WwanAsyncSetHomeProvider, wwan/WwanAsyncAuthChallenge, wwan/WwanAsyncSetDeviceServiceCommand, wwan/WwanAsyncSmsRead, wwan/WwanAsyncGetReadyInfo, wwan/WwanAsyncGetSignalState, wwan/WwanAsyncGetVisibleProviders, WwanAsyncSetSmsConfiguration, WwanAsyncSetServiceActivation, wwan/WwanAsyncGetPin, wwan/WWAN_ASYNC_GETSET_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wwan.h
apiname: 
-	WWAN_ASYNC_GETSET_TYPE
product: Windows
targetos: Windows
req.typenames: WWAN_ASYNC_GETSET_TYPE, *PWWAN_ASYNC_GETSET_TYPE
req.product: Windows 10 or later.
---

# _WWAN_ASYNC_GETSET_TYPE enumeration


## -description


The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests.


## -syntax


````
typedef enum _WWAN_ASYNC_GETSET_TYPE { 
  WwanAsyncGetDeviceCaps                         = 0,
  WwanAsyncGetReadyInfo                          = ,
  WwanAsyncGetRadioState                         = ,
  WwanAsyncSetRadioState                         = ,
  WwanAsyncGetPin                                = ,
  WwanAsyncSetPin                                = ,
  WwanAsyncGetPinList                            = ,
  WwanAsyncGetHomeProvider                       = ,
  WwanAsyncSetHomeProvider                       = ,
  WwanAsyncGetPreferredProviders                 = ,
  WwanAsyncSetPreferredProviders                 = ,
  WwanAsyncGetVisibleProviders                   = ,
  WwanAsyncGetRegisterState                      = ,
  WwanAsyncSetRegisterState                      = ,
  WwanAsyncGetPacketService                      = ,
  WwanAsyncSetPacketService                      = ,
  WwanAsyncGetSignalState                        = ,
  WwanAsyncSetSignalState                        = ,
  WwanAsyncGetConnect                            = ,
  WwanAsyncSetConnect                            = ,
  WwanAsyncGetProvisionedContexts                = ,
  WwanAsyncSetProvisionedContext                 = ,
  WwanAsyncSetServiceActivation                  = ,
  WwanAsyncGetSmsConfiguration                   = ,
  WwanAsyncSetSmsConfiguration                   = ,
  WwanAsyncSmsRead                               = ,
  WwanAsyncSmsSend                               = ,
  WwanAsyncSmsDelete                             = ,
  WwanAsyncSmsStatus                             = ,
  WwanAsyncSetVendorSpecific                     = ,
  WwanAsyncSetProfileIndex                       = ,
  WwanAsyncGetDeviceServices                     = ,
  WwanAsyncSubscribeDeviceServiceEvents          = ,
  WwanAsyncAuthChallenge                         = ,
  WwanAsyncUssdRequest                           = ,
  WwanAsyncSetPinEx                              = ,
  WwanAsyncGetPinEx get request.                 = ,
  WwanAsyncGetDeviceServiceCommand get request.  = ,
  WwanAsyncSetDeviceServiceCommand               = ,
  WWAN_ASYNC_GETSET_TYPE_MAX                     = 
} WWAN_ASYNC_GETSET_TYPE;
````


## -enum-fields




### -field WwanAsyncGetDeviceCaps

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569824">OID_WWAN_DEVICE_CAPS</a> get request.


### -field WwanAsyncGetReadyInfo

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569833">OID_WWAN_READY_INFO</a> get request.


### -field WwanAsyncGetRadioState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569832">OID_WWAN_RADIO_STATE</a> get request.


### -field WwanAsyncSetRadioState

Asynchronous OID_WWAN_RADIO_STATE set request.


### -field WwanAsyncGetPin

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569828">OID_WWAN_PIN</a> get request.


### -field WwanAsyncSetPin

Asynchronous OID_WWAN_PIN set request.


### -field WwanAsyncGetPinList

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569829">OID_WWAN_PIN_LIST</a> get request.


### -field WwanAsyncGetHomeProvider

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569826">OID_WWAN_HOME_PROVIDER</a> get request.


### -field WwanAsyncSetHomeProvider

Asynchronous OID_WWAN_HOME_PROVIDER set request.


### -field WwanAsyncGetPreferredProviders

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a> get request.


### -field WwanAsyncSetPreferredProviders

Asynchronous OID_WWAN_PREFERRED_PROVIDERS set request.


### -field WwanAsyncGetVisibleProviders

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a> get request.


### -field WwanAsyncGetRegisterState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569834">OID_WWAN_REGISTER_STATE</a> get request.


### -field WwanAsyncSetRegisterState

Asynchronous OID_WWAN_REGISTER_STATE set request.


### -field WwanAsyncGetPacketService

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569827">OID_WWAN_PACKET_SERVICE</a> get request.


### -field WwanAsyncSetPacketService

Asynchronous OID_WWAN_PACKET_SERVICE set request.


### -field WwanAsyncGetSignalState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569836">OID_WWAN_SIGNAL_STATE</a> get request.


### -field WwanAsyncSetSignalState

Asynchronous OID_WWAN_SIGNAL_STATE set request.


### -field WwanAsyncGetConnect

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569823">OID_WWAN_CONNECT</a> get request.


### -field WwanAsyncSetConnect

Asynchronous OID_WWAN_CONNECT set request.


### -field WwanAsyncGetProvisionedContexts

Asynchronous <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">OID_WWAN_PROVISIONED_CONTEXTS</a> get request.


### -field WwanAsyncSetProvisionedContext

Asynchronous OID_WWAN_PROVISIONED_CONTEXTS set request.


### -field WwanAsyncSetServiceActivation

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569835">OID_WWAN_SERVICE_ACTIVATION</a> set request.


### -field WwanAsyncGetSmsConfiguration

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569837">OID_WWAN_SMS_CONFIGURATION</a> get request.


### -field WwanAsyncSetSmsConfiguration

Asynchronous OID_WWAN_SMS_CONFIGURATION set request.


### -field WwanAsyncSmsRead

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569839">OID_WWAN_SMS_READ</a>



### -field WwanAsyncSmsSend

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569840">OID_WWAN_SMS_SEND</a>



### -field WwanAsyncSmsDelete

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569838">OID_WWAN_SMS_DELETE</a>



### -field WwanAsyncSmsStatus

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569841">OID_WWAN_SMS_STATUS</a>



### -field WwanAsyncSetVendorSpecific

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569842">OID_WWAN_VENDOR_SPECIFIC</a>



### -field WwanAsyncSetProfileIndex

Reserved.


### -field WwanAsyncGetDeviceServices

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440093">OID_WWAN_DEVICE_SERVICES</a> get request.


### -field WwanAsyncSubscribeDeviceServiceEvents

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440096">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a>



### -field WwanAsyncAuthChallenge

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440092">OID_WWAN_AUTH_CHALLENGE</a>



### -field WwanAsyncUssdRequest

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440100">OID_WWAN_USSD</a>



### -field WwanAsyncSetPinEx

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440095">OID_WWAN_PIN_EX</a> set request.


### -field WwanAsyncGetPinEx



### -field WwanAsyncGetDeviceServiceCommand



### -field WwanAsyncSetDeviceServiceCommand

Asynchronous OID_WWAN_DEVICE_SERVICE_COMMAND set request.


### -field WwanAsyncQueryDeviceServiceSupportedCommands



### -field WwanAsyncGetPreferredMultiCarrierProviders



### -field WwanAsyncSetPreferredMultiCarrierProviders



### -field WwanAsyncSetDeviceServiceSession



### -field WwanAsyncWriteDeviceServiceSession



### -field WwanAsyncSetNetworkIdleHint



### -field WwanAsyncSetPreshutdown



### -field WwanAsyncGetAtr



### -field WwanAsyncUiccOpenChannel



### -field WwanAsyncUiccCloseChannel



### -field WwanAsyncUiccSendApdu



### -field WwanAsyncUiccGetTerminalCapability



### -field WwanAsyncUiccSetTerminalCapability



### -field WwanAsyncGetPsMediaConfig



### -field WwanAsyncSetPsMediaConfig



### -field WwanAsyncGetSarConfig



### -field WwanAsyncSetSarConfig



### -field WwanAsyncGetSarTransmissionStatus



### -field WwanAsyncSetSarTransmissionStatus



### -field WwanAsyncGetNetworkBlacklist



### -field WwanAsyncSetNetworkBlacklist



### -field WwanAsyncGetLteAttachConfig



### -field WwanAsyncSetLteAttachConfig



### -field WwanAsyncGetLteAttachStatus



### -field WwanAsyncSetLteAttachStatus



### -field WwanAsyncGetProvisionedContextsV2



### -field WwanAsyncSetProvisionedContextV2



### -field WwanAsyncGetSysCap



### -field WwanAsyncGetDeviceCapsEx



### -field WwanAsyncGetUiccSlotMapping



### -field WwanAsyncSetUiccSlotMapping



### -field WwanAsyncGetUiccSlotInfo



### -field WwanAsyncGetModemConfigInfo



### -field WwanAsyncGetPcoStatus



### -field WwanAsyncUiccGetReset



### -field WwanAsyncUiccSetReset



### -field WwanAsyncSetDeviceReset



### -field WwanAsyncGetCellInfo



### -field WWAN_ASYNC_GETSET_TYPE_MAX

The maximum number of entries in the WWAN_ASYNC_GETSET_TYPE enumeration.


##### - WwanAsyncGetPinEx get request.

Asynchronous OID_WWAN_PIN_EX get request.


##### - WwanAsyncGetDeviceServiceCommand get request.

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440094">OID_WWAN_DEVICE_SERVICE_COMMAND</a>



## -see-also

<a href="https://msdn.microsoft.com/922b6b55-c332-4721-bbd1-571b0e154df3">MB Data Model</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_ASYNC_GETSET_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

