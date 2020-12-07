---
UID: NI:gnssdriver.IOCTL_GNSS_GET_CHIPSETINFO
title: IOCTL_GNSS_GET_CHIPSETINFO (gnssdriver.h)
description: The IOCTL_GNSS_GET_CHIPSETINFO control code is used by the GNSS manufacturing test application to get information about the GNSS chipset.
old-location: gnss\ioctl_gnss_get_chipsetinfo.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_GET_CHIPSETINFO IOCTL"]
ms.keywords: IOCTL_GNSS_GET_CHIPSETINFO, IOCTL_GNSS_GET_CHIPSETINFO control, IOCTL_GNSS_GET_CHIPSETINFO control code [Sensor Devices], gnss.ioctl_gnss_get_chipsetinfo, gnssdriver/IOCTL_GNSS_GET_CHIPSETINFO
req.header: gnssdriver.h
req.include-header: 
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_GNSS_GET_CHIPSETINFO
 - gnssdriver/IOCTL_GNSS_GET_CHIPSETINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_GET_CHIPSETINFO
---

# IOCTL_GNSS_GET_CHIPSETINFO IOCTL


## -description

The <b>IOCTL_GNSS_GET_CHIPSETINFO</b> 
   control code is used by the GNSS manufacturing test application to get information about the GNSS chipset. This information may be used by the test applications to decide which sets of tests should be executed, in which order, and map the response codes from the self tests into error conditions specific to the manufacturer or the chipset.

## -ioctlparameters

### -input-buffer

Set to NULL.

### -input-buffer-length

Set to 0.

### -output-buffer

A pointer to a <a href="/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_chipsetinfo">GNSS_CHIPSETINFO</a> structure.

### -output-buffer-length

Set to sizeof(GNSS_CHIPSETINFO).

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -remarks

<h3><a id="GNSS_test_application_notes"></a><a id="gnss_test_application_notes"></a><a id="GNSS_TEST_APPLICATION_NOTES"></a>GNSS test application notes</h3>
The GNSS test application must wait for the response from the GNSS driver and be resilient to the GNSS driver not responding.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver must respond with the information about the GNSS chipset.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
