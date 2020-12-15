---
UID: NC:wdfdevice.EVT_WDF_FILE_CLOSE
title: EVT_WDF_FILE_CLOSE (wdfdevice.h)
description: A driver's EvtFileClose callback function handles operations that must be performed when all of an application's accesses to a device have been closed.
old-location: wdf\evtfileclose.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_FILE_CLOSE callback function"]
ms.keywords: DFDeviceObjectGeneralRef_490bda33-9f36-43ab-9108-8622a3ea79b0.xml, EVT_WDF_FILE_CLOSE, EVT_WDF_FILE_CLOSE callback, EvtFileClose, EvtFileClose callback function, kmdf.evtfileclose, wdf.evtfileclose, wdfdevice/EvtFileClose
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
 - EVT_WDF_FILE_CLOSE
 - wdfdevice/EVT_WDF_FILE_CLOSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtFileClose
---

# EVT_WDF_FILE_CLOSE callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtFileClose</i> callback function handles operations that must be performed when all of an application's accesses to a device have been closed.

## -parameters

### -param FileObject 

[in]
A handle to a framework file object, which was previously received by the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function.

## -remarks

The framework calls a driver's <i>EvtFileClose</i> callback function when the last handle for a file object has been closed and released, and all outstanding I/O requests have been completed or canceled.

The device might not be in its working (D0) state.

Before the framework calls a driver's <i>EvtFileClose</i> callback function, it calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_cleanup">EvtFileCleanup</a> callback function.

The <i>EvtFileClose</i> callback function is called synchronously, in an arbitrary thread context. 

To register an <i>EvtFileClose</i> callback function, the driver must call the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

For more information about framework file objects and the <i>EvtFileClose</i> callback function, see <a href="/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a>
