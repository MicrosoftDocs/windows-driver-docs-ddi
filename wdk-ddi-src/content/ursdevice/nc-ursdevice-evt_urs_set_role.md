---
UID: NC:ursdevice.EVT_URS_SET_ROLE
title: EVT_URS_SET_ROLE
author: windows-driver-content
description: The URS class extension invokes this event callback when it requires the client driver to change the role of the controller.
old-location: buses\evt_urs_set_role.htm
old-project: usbref
ms.assetid: 287B674F-9692-47FA-AB92-F101270F7FC4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_urs_set_role, EvtUrsSetRole callback function [Buses], EvtUrsSetRole, EVT_URS_SET_ROLE, EVT_URS_SET_ROLE, ursdevice/EvtUrsSetRole, PFN_URS_SET_ROLE callback function pointer [Buses], PFN_URS_SET_ROLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
-	UserDefined
apilocation:
-	ursdevice.h
apiname:
-	PFN_URS_SET_ROLE
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# EVT_URS_SET_ROLE callback


## -description


The URS class extension invokes this event callback when it requires the client driver to change the role of the controller.


## -prototype


````
EVT_URS_SET_ROLE EvtUrsSetRole;

NTSTATUS EvtUrsSetRole(
  _In_ WDFDEVICE Device,
  _In_ URS_ROLE  Role
)
{ ... }

typedef EVT_URS_SET_ROLE PFN_URS_SET_ROLE;
````


## -parameters




#### - Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.


#### - Role [in]

A <a href="..\urstypes\ne-urstypes-_urs_role.md">URS_ROLE</a> type value that indicates the role to set for the controller device.


## -returns


If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.



## -remarks


 To register the client driver's implementation of the event callback the driver must set the  <b>EvtUrsSetRole</b> member of <a href="..\ursdevice\ns-ursdevice-_urs_config.md">URS_CONFIG</a> to a function pointer of the implementation method and then call the <a href="..\ursdevice\nf-ursdevice-ursdeviceinitialize.md">UrsDeviceInitialize</a> method by passing the populated structure. The driver must call the method after it creates the framework device object for the controller. 



## -see-also

<a href="..\ursdevice\nf-ursdevice-ursdeviceinitialize.md">UrsDeviceInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_URS_SET_ROLE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

