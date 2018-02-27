---
UID: TP:image
ms.assetid: 7b3b278b-3cff-355c-a263-9be80b8afde3
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Imaging devices


Overview of the Imaging devices technology.

To develop Imaging devices, you need these headers:

 * [ptpusd.h](..\ptpusd\index.md)
 * [scsiscan.h](..\scsiscan\index.md)
 * [sti.h](..\sti\index.md)
 * [stiusd.h](..\stiusd\index.md)
 * [usbscan.h](..\usbscan\index.md)
 * [wia_lh.h](..\wia_lh\index.md)
 * [wiadef.h](..\wiadef\index.md)
 * [wiadevd.h](..\wiadevd\index.md)
 * [wiamdef.h](..\wiamdef\index.md)
 * [wiamicro.h](..\wiamicro\index.md)
 * [wiamindr_lh.h](..\wiamindr_lh\index.md)
 * [wiatwcmp.h](..\wiatwcmp\index.md)
 * [wiautil.h](..\wiautil\index.md)

For the programming guide, see [Imaging devices](https://docs.microsoft.com/en-us/windows-hardware/drivers/image).

This section contains reference information for Windows Image Acquisition (WIA) drivers and for Still Imaging (STI) drivers. These drivers control devices, including scanners and cameras, that capture still images. For more information about these drivers, see Windows Image Acquisition Drivers and Still Image Drivers.

The following sections describe the interfaces, functions, structures, and properties used by WIA and STI drivers.

<table>
<tr>
<th>Section</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwiaminidrv_interface">IWiaMiniDrv Interface</mshelp:link>
</p>
</td>
<td>
<p>Interface for managing all communications between a WIA minidriver and the WIA service.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.wia_driver_services_library_functions">WIA Driver Services Library Functions</mshelp:link>
</p>
</td>
<td>
<p>Helper functions used by a WIA minidriver to manage device items and data transfers.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.wia_utility_library_functions_and_classes">WIA Utility Library Functions and Classes</mshelp:link>
</p>
</td>
<td>
<p>Utility functions and classes used by a WIA minidriver to support debugging and to perform common tasks.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwiaminidrvcallback_interface">IWiaMiniDrvCallBack Interface</mshelp:link>
</p>
</td>
<td>
<p>Callback interface for transferring status and image data between the WIA service and a WIA minidriver.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwiadrvitem_interface">IWiaDrvItem Interface</mshelp:link>
</p>
</td>
<td>
<p>Interface used by a WIA minidriver to manage a tree of WIA driver items.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwiaerrorhandler_interface">IWiaErrorHandler Interface</mshelp:link>
</p>
</td>
<td>
<p>Interface used by a WIA minidriver to provide error status and to support error recovery.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwiaimagefilter_interface">IWiaImageFilter Interface</mshelp:link>
</p>
</td>
<td>
<p>Interface implemented by an image processing filter and called by the WIA service to communicate with the filter.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwialog_interface_and_diagnostic_log_macros">IWiaLog Interface and Diagnostic Log Macros</mshelp:link>
</p>
</td>
<td>
<p>Interface and macros used by a WIA minidriver to record trace, error, and warning messages to a diagnostic log file.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwiasegmentationfilter_interface">IWiaSegmentationFilter Interface</mshelp:link>
</p>
</td>
<td>
<p>Interface used by a WIA minidriver to detect regions in a segmented image.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.iwiatransfercallback_interface">IWiaTransferCallback Interface</mshelp:link>
</p>
</td>
<td>
<p>Interface implemented by an image processing filter and called by the WIA service to initiate the processing of image streams.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.wia_microdriver_functions__structures__and_commands">WIA Microdriver Functions and Structures</mshelp:link>
</p>
</td>
<td>
<p>Functions and structures used by WIA microdrivers.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.wia_user_interface_extensions">WIA User Interface Extensions</mshelp:link>
</p>
</td>
<td>
<p>Interface used by device vendors to provide custom user interfaces for their devices.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.wia_structures">WIA Structures</mshelp:link>
</p>
</td>
<td>
<p>Structures used by driver-level WIA methods and functions.</p>
</td>
</tr>
<tr>
<td>
<p>
<mshelp:link tabindex="0" keywords="image.still_image_interfaces">Still Image Interfaces</mshelp:link>
</p>
</td>
<td>
<p>Interfaces, structures, data types, and control codes used by STI drivers.</p>
</td>
</tr>
</table>

Send comments about this topic to Microsoft

