---
UID: TP:gnss
ms.assetid: c486e5b4-8800-3452-8ea3-63402b0ba48a
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# 

## -description

Overview of the  technology.

To develop , you need these headers:

 * [gnssdriver.h](..\gnssdriver\index.md)

For the programming guide, see [](https://docs.microsoft.com/en-us/windows-hardware/drivers/gnss).

## Structures

| Title   | Description   |
| ---- |:---- |
| [GNSS_AGNSS_INJECT structure](..\gnssdriver\ns-gnssdriver-gnss_agnss_inject.md) | This structure defines the parameters for AGNSS injection. |
| [GNSS_AGNSS_INJECTBLOB structure](..\gnssdriver\ns-gnssdriver-gnss_agnss_injectblob.md) | This structure defines the format for AGNSS extended ephemeris injection. |
| [GNSS_AGNSS_INJECTPOSITION structure](..\gnssdriver\ns-gnssdriver-gnss_agnss_injectposition.md) | This structure defines the format for AGNSS position injection. |
| [GNSS_AGNSS_INJECTTIME structure](..\gnssdriver\ns-gnssdriver-gnss_agnss_injecttime.md) | This structure defines the format for AGNSS time injection. |
| [GNSS_AGNSS_REQUEST_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_agnss_request_param.md) | This structure defines AGNSS request parameters. |
| [GNSS_BREADCRUMBING_ALERT_DATA structure](..\gnssdriver\ns-gnssdriver-gnss_breadcrumbing_alert_data.md) | This structure contains alert information for when the breadcrumb buffer has reached a level where OS read operations should be performed. |
| [GNSS_BREADCRUMBING_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_breadcrumbing_param.md) | This structure contains the configuration passed into the start of breadcrumbing via IOCTL_GNSS_START_BREADCRUMBING. |
| [GNSS_BREADCRUMB_LIST structure](..\gnssdriver\ns-gnssdriver-gnss_breadcrumb_list.md) | This structure contains the response to an IOCTL_GNSS_POP_BREADCRUMBS. |
| [GNSS_BREADCRUMB_V1 structure](..\gnssdriver\ns-gnssdriver-gnss_breadcrumb_v1.md) | This structure contains an individual breadcrumb. The order and types of the fields are designed to pack densely. |
| [GNSS_CHIPSETINFO structure](..\gnssdriver\ns-gnssdriver-gnss_chipsetinfo.md) | This structure defines the specific data elements associated with the GNSS hardware. |
| [GNSS_CONTINUOUSTRACKING_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_continuoustracking_param.md) | This structure defines the parameters for a continuous tracking fix session. |
| [GNSS_CP_NI_INFO structure](..\gnssdriver\ns-gnssdriver-gnss_cp_ni_info.md) | This structure contains CP NI information. |
| [GNSS_CWTESTDATA structure](..\gnssdriver\ns-gnssdriver-gnss_cwtestdata.md) | This structure defines specific data elements associated with carrier wave test results returned from the driver. |
| [GNSS_DEVICE_CAPABILITY structure](..\gnssdriver\ns-gnssdriver-gnss_device_capability.md) | This structure is used to determine the device capabilities of the underlying GNSS engine. |
| [GNSS_DISTANCETRACKING_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_distancetracking_param.md) | This structure defines the parameters for a distance-based tracking fix session. |
| [GNSS_DRIVERCOMMAND_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_drivercommand_param.md) | This structure is used to send a command to the GNSS driver. |
| [GNSS_DRIVER_REQUEST_DATA structure](..\gnssdriver\ns-gnssdriver-gnss_driver_request_data.md) | This structure contains driver data request information. |
| [GNSS_ERRORINFO structure](..\gnssdriver\ns-gnssdriver-gnss_errorinfo.md) | This structure contains error information. |
| [GNSS_EVENT structure](..\gnssdriver\ns-gnssdriver-gnss_event.md) | This structure defines the information required for a GNSS event. |
| [GNSS_FIXDATA structure](..\gnssdriver\ns-gnssdriver-gnss_fixdata.md) | This structure defines the specific data elements associated with a GNSS fix returned from the driver. |
| [GNSS_FIXDATA_ACCURACY structure](..\gnssdriver\ns-gnssdriver-gnss_fixdata_accuracy.md) | This structure defines the accuracy details of a fix. |
| [GNSS_FIXDATA_BASIC structure](..\gnssdriver\ns-gnssdriver-gnss_fixdata_basic.md) | This structure defines basic position information. |
| [GNSS_FIXDATA_SATELLITE structure](..\gnssdriver\ns-gnssdriver-gnss_fixdata_satellite.md) | This structure defines satellite-related information of a fix. |
| [GNSS_FIXSESSION_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_fixsession_param.md) | This structure defines the parameters used by the GNSS adapter to start a fix session. |
| [GNSS_GEOFENCES_TRACKINGSTATUS_DATA structure](..\gnssdriver\ns-gnssdriver-gnss_geofences_trackingstatus_data.md) | This structure is used by the GNSS engine to notify of any changes in the tracking status while tracking a set of previously created geofences. |
| [GNSS_GEOFENCE_ALERT_DATA structure](..\gnssdriver\ns-gnssdriver-gnss_geofence_alert_data.md) | This structure is used by the GNSS engine to notify a geofence breach alert. |
| [GNSS_GEOFENCE_CREATE_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_geofence_create_param.md) | This structure defines the parameters for creating a geofence in the GNSS engine. |
| [GNSS_GEOFENCE_CREATE_RESPONSE structure](..\gnssdriver\ns-gnssdriver-gnss_geofence_create_response.md) | This structure defines the response expected from the GNSS engine when a new geofence is created. |
| [GNSS_GEOFENCE_DELETE_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_geofence_delete_param.md) | This structure is used for deleting a geofence. |
| [GNSS_GEOREGION structure](..\gnssdriver\ns-gnssdriver-gnss_georegion.md) | This structure defines the geographical shape of a geofence. |
| [GNSS_GEOREGION_CIRCLE structure](..\gnssdriver\ns-gnssdriver-gnss_georegion_circle.md) | This structure is used for defining a circular geofence. |
| [GNSS_LKGFIX_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_lkgfix_param.md) | This structure is not used currently by the system and is not required to be implemented. |
| [GNSS_NI_REQUEST_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_ni_request_param.md) | This structure contains the NI request parameters. |
| [GNSS_NI_RESPONSE structure](..\gnssdriver\ns-gnssdriver-gnss_ni_response.md) | This structure contains NI request response information. |
| [GNSS_NMEA_DATA structure](..\gnssdriver\ns-gnssdriver-gnss_nmea_data.md) | This structure contains generic (non-parsed) NMEA data. |
| [GNSS_PLATFORM_CAPABILITY structure](..\gnssdriver\ns-gnssdriver-gnss_platform_capability.md) | This structure is used to communicate the platform/HLOS capabilities to the underlying GNSS driver. |
| [GNSS_SATELLITEINFO structure](..\gnssdriver\ns-gnssdriver-gnss_satelliteinfo.md) | This structure defines satellite-related information of a fix. |
| [GNSS_SELFTESTCONFIG structure](..\gnssdriver\ns-gnssdriver-gnss_selftestconfig.md) | This structure defines the specific data elements associated with a carrier wave test results returned from the driver. |
| [GNSS_SELFTESTRESULT structure](..\gnssdriver\ns-gnssdriver-gnss_selftestresult.md) | This structure defines the specific data elements associated with a carrier wave test results returned from the driver. |
| [GNSS_SINGLESHOT_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_singleshot_param.md) | This structure defines the parameters for a single-shot fix session. |
| [GNSS_STOPFIXSESSION_PARAM structure](..\gnssdriver\ns-gnssdriver-gnss_stopfixsession_param.md) | This structure is used to stop an active fix session. |
| [GNSS_SUPL_CERT_CONFIG structure](..\gnssdriver\ns-gnssdriver-gnss_supl_cert_config.md) | This structure contains SUPL certificate information. |
| [GNSS_SUPL_HSLP_CONFIG structure](..\gnssdriver\ns-gnssdriver-gnss_supl_hslp_config.md) | This structure contains SUPL H-SLP configuration information. |
| [GNSS_SUPL_NI_INFO structure](..\gnssdriver\ns-gnssdriver-gnss_supl_ni_info.md) | This structure contains the requested SUPL NI information. |
| [GNSS_SUPL_VERSION structure](..\gnssdriver\ns-gnssdriver-gnss_supl_version.md) | This structure contains SUPL version information. |
| [GNSS_V2UPL_CONFIG structure](..\gnssdriver\ns-gnssdriver-gnss_v2upl_config.md) | This structure contains V2UPL configuration information. |
| [GNSS_V2UPL_NI_INFO structure](..\gnssdriver\ns-gnssdriver-gnss_v2upl_ni_info.md) | This structure contains V2UPL NI information. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [GNSS_AGNSS_REQUEST_TYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_agnss_request_type.md) | This enumeration indicates the type of AGNSS injection request represented by the GNSS_AGNSS_REQUEST_PARAM structure. |
| [GNSS_DRIVERCOMMAND_TYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_drivercommand_type.md) | This enumeration indicates the type of driver command or configuration for the GNSS driver provided in the GNSS_DRIVERCOMMAND_PARAM structure. |
| [GNSS_DRIVER_REQUEST enumeration](..\gnssdriver\ne-gnssdriver-gnss_driver_request.md) | GNSS_DRIVER_REQUEST enumerates the GNSS driver data request types. |
| [GNSS_EVENT_TYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_event_type.md) | This enumeration indicates the type of an event and is used by the GNSS_EVENT structure. |
| [GNSS_FIXSESSIONTYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_fixsessiontype.md) | This enumeration indicates the type of location fix needed by the GNSS adapter when it issues an IOCTL_GNSS_START_FIXSESSION control code. This enumeration is set within the GNSS_FIXSESSION_PARAM structure. |
| [GNSS_GEOFENCE_STATE enumeration](..\gnssdriver\ne-gnssdriver-gnss_geofence_state.md) | GNSS_GEOFENCE_STATE enumerates the various states of a single geofence. |
| [GNSS_GEOREGIONTYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_georegiontype.md) | This enumeration is used for defining a geographical shape. A shape is used to define a geofence. Windows 10 currently only supports circular geofences. |
| [GNSS_NI_NOTIFICATION_TYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_ni_notification_type.md) | GNSS_NI_NOTIFICATION_TYPE enumerates network-initialized (NI) notification types. |
| [GNSS_NI_PLANE_TYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_ni_plane_type.md) | This enumeration indicates the plane type of a network initiated (NI) request represented by the GNSS_NI_REQUEST_PARAM structure. |
| [GNSS_NI_REQUEST_TYPE enumeration](..\gnssdriver\ne-gnssdriver-gnss_ni_request_type.md) | This enumeration indicates the network initiated (NI) request type represented by the GNSS_NI_REQUEST_PARAM structure. |
| [GNSS_NI_USER_RESPONSE enumeration](..\gnssdriver\ne-gnssdriver-gnss_ni_user_response.md) | This enumeration indicates the user’s response to a network initiated (NI) request, which is represented by the GNSS_NI_RESPONSE structure. |
| [GNSS_SUPL_CERT_ACTION enumeration](..\gnssdriver\ne-gnssdriver-gnss_supl_cert_action.md) | This enumeration indicates the action to take upon receipt of the SUPL certificate, which is defined by the GNSS_SUPL_CERT_CONFIG structure. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_GNSS_CONFIG_SUPL_CERT IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_config_supl_cert.md) | The IOCTL_GNSS_CONFIG_SUPL_CERT control code is used by the GNSS adapter to set SUPL certificates. |
| [IOCTL_GNSS_CREATE_GEOFENCE IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_create_geofence.md) | The IOCTL_GNSS_CREATE_GEOFENCE control code is used by the GNSS adapter to create a geofence. |
| [IOCTL_GNSS_DELETE_GEOFENCE IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_delete_geofence.md) | The IOCTL_GNSS_DELETE_GEOFENCE control code is used by the GNSS adapter to delete a previously created geofence. |
| [IOCTL_GNSS_EXECUTE_CWTEST IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_execute_cwtest.md) | The IOCTL_GNSS_EXECUTE_CWTEST control code is used by the GNSS manufacturing test application to start a carrier wave test and get the measurement. The test application must wait for the result before starting another iteration of the measurement. |
| [IOCTL_GNSS_EXECUTE_SELFTEST IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_execute_selftest.md) | The IOCTL_GNSS_EXECUTE_SELFTEST control code is used by the GNSS manufacturing test application to initiate a self test in the GNSS lower stack. |
| [IOCTL_GNSS_GET_CHIPSETINFO IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_get_chipsetinfo.md) | The IOCTL_GNSS_GET_CHIPSETINFO control code is used by the GNSS manufacturing test application to get information about the GNSS chipset. |
| [IOCTL_GNSS_GET_DEVICE_CAPABILITY IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_get_device_capability.md) | The IOCTL_GNSS_GET_DEVICE_CAPABILITY control code is used by the GNSS adapter to get the GNSS driver and device capabilities. |
| [IOCTL_GNSS_GET_FIXDATA IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_get_fixdata.md) | The IOCTL_GNSS_GET_FIXDATA control code is used by the GNSS adapter to register to receive the next fix data from an active fix session. |
| [IOCTL_GNSS_INJECT_AGNSS IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_inject_agnss.md) | The IOCTL_GNSS_INJECT_AGNSS control code is used by the GNSS adapter to inject AGNSS data into the driver. This IOCTL is sent as a result of the driver previously responding to a pending IOCTL_GNSS_LISTEN_AGNSS request. |
| [IOCTL_GNSS_LISTEN_AGNSS IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_agnss.md) | The IOCTL_GNSS_LISTEN_AGNSS control code is used by the GNSS adapter to start listening for AGNSS requests issued by the GNSS driver. |
| [IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_breadcrumbing_alert.md) | The IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code is used to request alert information from GNSS_BREADCRUMBING_ALERT_DATA when the breadcrumbing buffer has reached a level at which OS read operations should be performed. |
| [IOCTL_GNSS_LISTEN_DRIVER_REQUEST IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_driver_request.md) | The IOCTL_GNSS_LISTEN_DRIVER_REQUEST control code is used by the GNSS driver to get data from the HLOS. |
| [IOCTL_GNSS_LISTEN_ERROR IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_error.md) | The IOCTL_GNSS_LISTEN_ERROR control code is used to start listening for ERROR events from the driver. |
| [IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_geofences_trackingstatus.md) | The IOCTL_GNSS_LISTEN_GEOFENCES_TRACKINGSTATUS control code is used to receive geofence tracking status from the driver. |
| [IOCTL_GNSS_LISTEN_GEOFENCE_ALERT IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_geofence_alert.md) | The IOCTL_GNSS_LISTEN_GEOFENCE_ALERT control code is used to start listening for geofence alerts from the driver. |
| [IOCTL_GNSS_LISTEN_NI IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_ni.md) | The IOCTL_GNSS_LISTEN_NI control code is used to start listening for a SUPL NI request. |
| [IOCTL_GNSS_LISTEN_NMEA IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_nmea.md) | The IOCTL_GNSS_LISTEN_NMEA control code is used to start listening for NMEA events from the driver. |
| [IOCTL_GNSS_MODIFY_FIXSESSION IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_modify_fixsession.md) | The IOCTL_GNSS_MODIFY_FIXSESSION control code is used by the GNSS adapter to modify the fix session parameters of an active fix session. |
| [IOCTL_GNSS_POP_BREADCRUMBS IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_pop_breadcrumbs.md) | The IOCTL_GNSS_POP_BREADCRUMBS control code is used to request a list of breadcrumbs contained in GNSS_BREADCRUMB_LIST. |
| [IOCTL_GNSS_RESPOND_NI IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_respond_ni.md) | The IOCTL_GNSS_RESPOND_NI control code is used by the GNSS adapter to respond to an NI request that was asynchronously communicated to it by the GNSS driver through the resolution of an IOCTL_GNSS_LISTEN_NI request. |
| [IOCTL_GNSS_SEND_DRIVERCOMMAND IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_send_drivercommand.md) | The IOCTL_GNSS_SEND_DRIVERCOMMAND control code is used by the GNSS adapter to execute well-defined commands on the driver and also to set driver configuration parameters. |
| [IOCTL_GNSS_SEND_PLATFORM_CAPABILITY IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_send_platform_capability.md) | The IOCTL_GNSS_SEND_PLATFORM_CAPABILITY control code is used by the GNSS adapter to communicate the various location-specific platform capabilities. |
| [IOCTL_GNSS_SET_SUPL_HSLP IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_set_supl_hslp.md) | The IOCTL_GNSS_SET_SUPL_HSLP control code is used by the GNSS adapter to set the SUPL H-SLP address. |
| [IOCTL_GNSS_SET_V2UPL_CONFIG IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_set_v2upl_config.md) | The IOCTL_GNSS_SET_V2UPL_CONFIG control code is used by the GNSS adapter to set configuration for v2 user plane location for CDMA, which consist of the MPC address, and in testing mode, potentially the PDE address. |
| [IOCTL_GNSS_START_BREADCRUMBING IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_start_breadcrumbing.md) | The IOCTL_GNSS_START_BREADCRUMBING control code is used to start and configure breadcrumbing. |
| [IOCTL_GNSS_START_FIXSESSION IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_start_fixsession.md) | The IOCTL_GNSS_START_FIXSESSION control code is used by the GNSS adapter to start a fix session. |
| [IOCTL_GNSS_STOP_BREADCRUMBING IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_stop_breadcrumbing.md) | The IOCTL_GNSS_STOP_BREADCRUMBING control code is used to stop breadcrumbing. |
| [IOCTL_GNSS_STOP_FIXSESSION IOCTL](..\gnssdriver\ni-gnssdriver-ioctl_gnss_stop_fixsession.md) | The IOCTL_GNSS_STOP_FIXSESSION control code is used by the GNSS adapter to stop an active fix session. |
