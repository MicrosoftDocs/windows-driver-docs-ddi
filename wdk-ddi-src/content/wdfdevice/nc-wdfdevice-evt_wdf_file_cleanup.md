---
UID: NC:wdfdevice.EVT_WDF_FILE_CLEANUP
title: EVT_WDF_FILE_CLEANUP (wdfdevice.h)
description: A driver's EvtFileCleanup callback function handles operations that must be performed when an application is closing all accesses to a device.
old-location: wdf\evtfilecleanup.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_FILE_CLEANUP callback function"]
ms.keywords: DFDeviceObjectGeneralRef_e784bb8d-f1f3-48ac-94c5-d88f2517efd1.xml, EVT_WDF_FILE_CLEANUP, EVT_WDF_FILE_CLEANUP callback, EvtFileCleanup, EvtFileCleanup callback function, kmdf.evtfilecleanup, wdf.evtfilecleanup, wdfdevice/EvtFileCleanup
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_FILE_CLEANUP
 - wdfdevice/EVT_WDF_FILE_CLEANUP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtFileCleanup
---

# EVT_WDF_FILE_CLEANUP callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtFileCleanup</i> callback function handles operations that must be performed when an application is closing all accesses to a device.

## -parameters

### -param FileObject 

[in]
A handle to a framework file object, which was previously received by the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function.

## -remarks

The framework calls a driver's <i>EvtFileCleanup</i> callback function when the last handle to the specified file object has been closed. (Because of outstanding I/O requests, this handle might not have been released.) 

After the framework calls a driver's <i>EvtFileCleanup</i> callback function, it calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback function.

The <i>EvtFileCleanup</i> callback function is called synchronously, in the context of the thread that closed the last file object handle. 

To register an <i>EvtFileCleanup</i> callback function, the driver must call the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

For more information about framework file objects and the <i>EvtFileCleanup</i> callback function, see <a href="/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a>
