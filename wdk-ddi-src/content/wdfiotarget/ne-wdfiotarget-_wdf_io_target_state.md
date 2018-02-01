---
UID: NE:wdfiotarget._WDF_IO_TARGET_STATE
title: "_WDF_IO_TARGET_STATE"
author: windows-driver-content
description: The WDF_IO_TARGET_STATE enumeration specifies the states that an I/O target can be in.
old-location: wdf\wdf_io_target_state.htm
old-project: wdf
ms.assetid: 0189a83d-da46-49f1-99b8-8fb920009804
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoTargetClosedForQueryRemove, WDF_IO_TARGET_STATE enumeration, wdfiotarget/WdfIoTargetStarted, WdfIoTargetStarted, wudfddi_types/WdfIoTargetClosed, *PWDF_IO_TARGET_STATE, DFIOTargetRef_0dbd75b8-eb70-4996-8a13-80fb90f86dca.xml, wdfiotarget/WdfIoTargetStateUndefined, wdf.wdf_io_target_state, wudfddi_types/WdfIoTargetDeleted, wudfddi_types/WdfIoTargetStarted, _WDF_IO_TARGET_STATE, wdfiotarget/WdfIoTargetClosed, WdfIoTargetClosed, kmdf.wdf_io_target_state, WdfIoTargetDeleted, WdfIoTargetStateUndefined, wdfiotarget/WdfIoTargetClosedForQueryRemove, wdfiotarget/WdfIoTargetStopped, wudfddi_types/WdfIoTargetPurged, wudfddi_types/WDF_IO_TARGET_STATE, wudfddi_types/WdfIoTargetStateUndefined, wdfiotarget/WdfIoTargetDeleted, PWDF_IO_TARGET_STATE enumeration pointer, PWDF_IO_TARGET_STATE, wudfddi_types/WdfIoTargetClosedForQueryRemove, WdfIoTargetStopped, wdfiotarget/PWDF_IO_TARGET_STATE, wdfiotarget/WDF_IO_TARGET_STATE, WdfIoTargetPurged, wdfiotarget/WdfIoTargetPurged, wudfddi_types/WdfIoTargetStopped, WDF_IO_TARGET_STATE, wudfddi_types/PWDF_IO_TARGET_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
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
-	wdfiotarget.h
-	wudfddi_types.h
apiname:
-	WDF_IO_TARGET_STATE
product: Windows
targetos: Windows
req.typenames: "*PWDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE"
req.product: Windows 10 or later.
---

# _WDF_IO_TARGET_STATE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_STATE</b> enumeration specifies the states that an I/O target can be in.


## -syntax


````
typedef enum _WDF_IO_TARGET_STATE { 
  WdfIoTargetStateUndefined        = 0,
  WdfIoTargetStarted               = 1,
  WdfIoTargetStopped               = 2,
  WdfIoTargetClosedForQueryRemove  = 3,
  WdfIoTargetClosed                = 4,
  WdfIoTargetDeleted               = 5,
  WdfIoTargetPurged                = 6
} WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE;
````


## -enum-fields




### -field WdfIoTargetStateUndefined

Reserved for internal use.


### -field WdfIoTargetStarted

The I/O target is started and can process I/O requests.


### -field WdfIoTargetStopped

The I/O target is temporarily stopped and cannot process I/O requests.


### -field WdfIoTargetClosedForQueryRemove

The I/O target's underlying device might be removed in the near future.


### -field WdfIoTargetClosed

The I/O target is permanently stopped and cannot process I/O requests. 


### -field WdfIoTargetDeleted

The I/O target's underlying device has been removed.


### -field WdfIoTargetPurged

The I/O target is temporarily purged and cannot receive or process I/O requests. This constant is available starting in KMDF 1.11.


## -remarks


To obtain an I/O target's current state, call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetgetstate.md">WdfIoTargetGetState</a>.

For more information about states for I/O targets, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetgetstate.md">WdfIoTargetGetState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_STATE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

