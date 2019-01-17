---
UID: NI:gnssdriver.IOCTL_GNSS_SET_SUPL_HSLP
title: IOCTL_GNSS_SET_SUPL_HSLP
description: The IOCTL_GNSS_SET_SUPL_HSLP control code is used by the GNSS adapter to set the SUPL H-SLP address.
old-location: gnss\ioctl_gnss_set_supl_hslp.htm
tech.root: gnss
ms.assetid: A6056EB4-4CEA-4C80-A3CA-1B6B81F47889
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_SET_SUPL_HSLP, IOCTL_GNSS_SET_SUPL_HSLP control, IOCTL_GNSS_SET_SUPL_HSLP control code [Sensor Devices], gnss.ioctl_gnss_set_supl_hslp, gnssdriver/IOCTL_GNSS_SET_SUPL_HSLP
ms.topic: ioctl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_SET_SUPL_HSLP
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_SET_SUPL_HSLP IOCTL


## -description


The <b>IOCTL_GNSS_SET_SUPL_HSLP</b> control code is used by the GNSS adapter to set the SUPL H-SLP address.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925229">GNSS_SUPL_HSLP_CONFIG</a> structure.


### -input-buffer-length

Set to sizeof(GNSS_SUPL_HSLP_CONFIG).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



The driver sets one of the following NTSTATUS values to indicate result.

<ul>
<li>
<b>STATUS_SUCCESS</b>, when the driver processes the SUPL H-SLP information successfully.

</li>
<li>
<b>Failed</b>, when the driver does not process the SUPL H-SLP information successfully.

</li>
<li>
<b>Ignored</b>, when the driver ignores the SUPL H-SLP information.

</li>
</ul>
<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver must pass the H-SLP information, contained in the input structure, to the SUPL component which should connect to the server address specified by the H-SLP.

If the certificate with the same name is injected again, the GNSS driver should overwrite the previous certificate with the same name.

The H-SLP address is always in the form of a FQDN.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

