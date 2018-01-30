---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal method
author: windows-driver-content
description: The UnregisterPhysicalConnectionFromExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionFromExternal.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnectionfromexternal.htm
old-project: audio
ms.assetid: 82d71ee0-13e1-4f7f-ad81-9e1b6e484052
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal, IUnregisterPhysicalConnection, IUnregisterPhysicalConnection interface [Audio Devices], UnregisterPhysicalConnectionFromExternal method, audio.iunregisterphysicalconnection_unregisterphysicalconnectionfromexternal, UnregisterPhysicalConnectionFromExternal, UnregisterPhysicalConnectionFromExternal method [Audio Devices], IUnregisterPhysicalConnection interface, IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal, audmp-routines_24091cfd-dee9-400a-8cb6-f3a4a44ed9c5.xml, UnregisterPhysicalConnectionFromExternal method [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal method


## -description


The <b>UnregisterPhysicalConnectionFromExternal</b> method deletes the registration of a physical connection that was registered by a previous call to <a href="..\portcls\nf-portcls-pcregisterphysicalconnectionfromexternal.md">PcRegisterPhysicalConnectionFromExternal</a>.


## -syntax


````
NTSTATUS UnregisterPhysicalConnectionFromExternal(
  [in] PDEVICE_OBJECT  DeviceObject,
  [in] PUNICODE_STRING FromString,
  [in] ULONG           FromPin,
  [in] PUNKNOWN        ToUnknown,
  [in] ULONG           ToPin
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param FromString [in]

Pointer to a null-terminated Unicode string that contains the name of the external filter that supplies the connection's data source pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the data source (output) pin on the external filter that is named by the <i>FromString</i> parameter.


### -param ToUnknown [in]

Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink pin.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the data sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.


## -returns


<b>UnregisterPhysicalConnectionFromExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.



## -see-also

<a href="..\portcls\nn-portcls-iunregisterphysicalconnection.md">IUnregisterPhysicalConnection</a>

<a href="..\portcls\nf-portcls-pcregisterphysicalconnectionfromexternal.md">PcRegisterPhysicalConnectionFromExternal</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\portcls\nn-portcls-iport.md">IPort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

