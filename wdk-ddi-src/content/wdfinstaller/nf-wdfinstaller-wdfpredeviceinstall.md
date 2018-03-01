---
UID: NF:wdfinstaller.WdfPreDeviceInstall
title: WdfPreDeviceInstall function
author: windows-driver-content
description: The co-installer's WdfPreDeviceInstall function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service.
old-location: wdf\wdfpredeviceinstall.htm
old-project: wdf
ms.assetid: 2da4b4ea-1cbb-43f7-9001-44b07a3e9ef7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFCoinstallerRef_0d1aca8b-f318-42c4-a74d-bd69d272ceec.xml, WdfPreDeviceInstall, WdfPreDeviceInstall function, kmdf.wdfpredeviceinstall, wdf.wdfpredeviceinstall, wdfinstaller/WdfPreDeviceInstall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	N/A
-	N/A.dll
api_name:
-	WdfPreDeviceInstall
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WdfPreDeviceInstall function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The co-installer's <b>WdfPreDeviceInstall</b> function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service. 


## -syntax


````
ULONG WdfPreDeviceInstall(
  _In_     LPCWSTR InfPath,
  _In_opt_ LPCWSTR InfSectionName
);
````


## -parameters




### -param InfPath [in]

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <a href="https://msdn.microsoft.com/1fbe6289-2ca8-4ca8-b004-ecf513f9b0bd">GetCurrentDirectory</a>, which is described in the Microsoft Windows SDK.


### -param InfSectionName [in, optional]

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/installing-the-framework-s-co-installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


## -returns



<b>WdfPreDeviceInstall</b> returns <b>ERROR_SUCCESS</b> if the operation succeeds. Otherwise, the function returns one of the additional <b>ERROR_XXX</b> values that are defined in Winerror.h.




## -remarks



The installer for the framework-based drivers of a non-PnP device must call <b>WdfPreDeviceInstall</b> or <a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstallex.md">WdfPreDeviceInstallEx</a> before the installer calls <a href="https://msdn.microsoft.com/47288924-3294-4a50-b27d-7df80d5c957c">CreateService</a>.

To obtain the address of the co-installer's <b>WdfPreDeviceInstall</b> function, the installer must call <a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a> after the installer has called <a href="https://msdn.microsoft.com/d936b4dd-058c-48e1-834b-b47ef6d8ef65">LoadLibrary</a> to load the co-installer.

If the co-installer determines that the computer must be restarted to complete the driver installation (typically because an older version of the framework was previously installed), <b>WdfPreDeviceInstall</b> informs the Plug and Play (PnP) manager. The PnP manager then prompts the user that a restart is necessary. 

For more information about the <b>WdfPreDeviceInstall</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://msdn.microsoft.com/99676d85-feb2-482c-a91b-cfc48be5904c">Installing a Non-PnP Driver</a>. For more information about <a href="https://msdn.microsoft.com/47288924-3294-4a50-b27d-7df80d5c957c">CreateService</a>, <a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a>, and <a href="https://msdn.microsoft.com/d936b4dd-058c-48e1-834b-b47ef6d8ef65">LoadLibrary</a>, see the Microsoft Windows SDK documentation.


#### Examples

For a code example that uses the <b>WdfPreDeviceInstall</b> function, see the installer for the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">NONPNP</a> sample.

<div class="code"></div>



## -see-also

<a href="..\wdfinstaller\nf-wdfinstaller-wdfpostdeviceinstall.md">WdfPostDeviceInstall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPreDeviceInstall function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

