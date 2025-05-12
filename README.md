PDS4 Imaging Discipline Data Dictionary User's Guide  
[Last edited](#edit-history): 2025-05-12  
  
# Introduction  
1. Purpose of this User's Guide  
    - This User's Guide provides an overview of the Imaging Discipline Data Dictionary. The guide details how to include the dictionary in a PDS4 label, describes the organization of the dictionary's classes and attributes, provides definitions for these classes and attributes, and lists example excerpts from labels that use them.  
2. Audience  
    - This User's Guide should be useful to data providers intending to archive Imaging data with PDS as well as PDS Nodes who are working with these data providers.  
  
# Overview of the Imaging Discipline Data Dictionary  
The Imaging Discipline Data Dictionary contains classes and attributes specific to the Imaging discipline.  
Steward: Trent Hare, PDS Imaging Node, thare@usgs.gov  
  
# Document Outline  
1. [How to Include the Imaging Discipline Data Dictionary in a PDS4 Label](#how-to-include-the-Imaging-Discipline-data-dictionary-in-a-pds4-label)  
2. [Organization of Classes and Attributes](#organization-of-classes-and-attributes)  
    1. [Class Organization](#class-organization)  
    2. [Attributes by Class](#attributes-by-class)  
3. [Definitions](#definitions)  
    1. [Classes (in alphabetical order)](#classes-in-alphabetical-order)  
    2. [Attributes (in alphabetical order)](#attributes-in-alphabetical-order)  
4. [Examples](#examples)  
5. [Edit History](#edit-history)  
  
# How to Include the Imaging Discipline Data Dictionary in a PDS4 Label  
The dictionary consists of a set of files with names in the form PDS4_IMG_xxxx_yyyy.ext, where  
- xxxx = the PDS4 Information Model version, e.g. 1O00  
- yyyy = the Imaging Discipline Data Dictionary version, e.g. 1920  
  
and the file extensions are  
  
- .csv = A comma-separated value table of dictionary attributes  
- .JSON = The dictionary contents in JSON format  
- .sch = The dictionary "rules" as an XML Schematron file  
- .txt = The report generated when the dictionary was built  
- .xml = The PDS4 label that describes this set of files  
- .xsd = The dictionary contents as an XML schema file  
  
Only the schema and Schematron files are needed for validating a PDS4 label.  
  
The latest version of this dictionary may be found on the PDS web site at https://pds.nasa.gov/datastandards/dictionaries/index.shtml#img.  
  
The following is an example showing the use of this dictionary in a PDS4 label.  
  
```
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1O00.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<?xml-model href="https://pds.nasa.gov/pds4/img/v1/PDS4_IMG_1O00_1920.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<Product_Observational xmlns="http://pds.nasa.gov/pds4/pds/v1"
    xmlns:img="http://pds.nasa.gov/pds4/img/v1"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1O00.xsd
                        https://pds.nasa.gov/pds4/img/v1/PDS4_IMG_1O00_1920.xsd">
```  
  
The following is a schematic example showing the location of every Imaging Discipline Data Dictionary class and attribute in a PDS4 label. Note that not all classes and attributes may be mutually compatible, and the example does not include any recursion, even if recursion is allowed.  
```
<Observation_Area>
  ...
  <Discipline_Area>
    <img:Correction_Parameter>
      <img:sequence_number/>
      <img:name/>
      <img:id/>
      <img:value_number/>
      <img:value_string/>
    </img:Correction_Parameter>
    <img:Data_Processing>
      <img:active_flag/>
      <img:processing_venue/>
      <img:processing_algorithm/>
      <img:sequence_number/>
    </img:Data_Processing>
    <img:Data_Processing_File>
      <img:description/>
      <img:name/>
      <img:Internal_Reference>
      </img:Internal_Reference>
      <img:External_Reference>
      </img:External_Reference>
    </img:Data_Processing_File>
    <img:Device_Parameters>
      <img:device_name/>
      <img:device_id/>
      <img:sequence_number/>
    </img:Device_Parameters>
    <img:Imaging>
      <img:Local_Internal_Reference>
      </img:Local_Internal_Reference>
      <img:Brightness_Correction>
        <img:active_flag/>
        <img:processing_venue/>
        <img:processing_algorithm/>
        <img:sequence_number/>
        <img:Brightness_Correction_File>
          <img:description/>
          <img:name/>
          <img:Internal_Reference>
          </img:Internal_Reference>
          <img:External_Reference>
          </img:External_Reference>
        </img:Brightness_Correction_File>
        <img:Brightness_Correction_Image>
          <img:Internal_Reference>
          </img:Internal_Reference>
          <img:Brightness_Correction_Linear>
            <img:brightness_scale/>
            <img:brightness_offset/>
          </img:Brightness_Correction_Linear>
          <img:Brightness_Correction_HSI_Linear>
            <img:brightness_scale/>
            <img:brightness_offset/>
          </img:Brightness_Correction_HSI_Linear>
        </img:Brightness_Correction_Image>
      </img:Brightness_Correction>
      <img:Col_Sum>
        <img:download_priority/>
        <img:product_flag/>
      </img:Col_Sum>
      <img:Color_Filter_Array>
        <img:color_filter_array_type/>
        <img:active_flag/>
        <img:color_filter_array_state/>
        <img:processing_venue/>
        <img:processing_algorithm/>
        <img:sequence_number/>
      </img:Color_Filter_Array>
      <img:Color_Processing>
        <img:color_space/>
        <img:active_flag/>
        <img:color_component/>
        <img:processing_venue/>
        <img:illuminant/>
        <img:processing_algorithm/>
        <img:encoded_display_gamma/>
        <img:sequence_number/>
        <img:color_dn_scaling_method/>
        <img:color_dn_scaling_factor/>
        <img:Onboard_Responsivity>
          <img:responsivity_factor_r/>
          <img:responsivity_factor_g/>
          <img:responsivity_factor_b/>
        </img:Onboard_Responsivity>
        <img:Onboard_Color_Matrix>
          <img:onboard_R_r/>
          <img:onboard_R_g/>
          <img:onboard_R_b/>
          <img:onboard_G_r/>
          <img:onboard_G_g/>
          <img:onboard_G_b/>
          <img:onboard_B_r/>
          <img:onboard_B_g/>
          <img:onboard_B_b/>
        </img:Onboard_Color_Matrix>
      </img:Color_Processing>
      <img:Dark_Current_Correction>
        <img:striping_count/>
        <img:active_flag/>
        <img:striping_overlap_rows/>
        <img:processing_venue/>
        <img:processing_algorithm/>
        <img:sequence_number/>
      </img:Dark_Current_Correction>
      <img:Data_Quality>
        <img:dq_band/>
        <img:dq_bayer_cell/>
        <img:comment/>
        <img:no_signal_count/>
        <img:above_aft_flag/>
        <img:below_aft_flag/>
        <img:full_well_limit_flag/>
        <img:data_received/>
        <img:image_corrupt_flag/>
        <img:missing_temperature_flag/>
        <img:out_of_focus_flag/>
        <img:saturated_flag/>
        <img:sequence_terminated_flag/>
        <img:wrong_filter_flag/>
        <img:wrong_pointing_flag/>
        <img:wrong_zoom_flag/>
        <img:zero_value_pixels_flag/>
        <img:Hot_Pixel>
          <img:pixel_count/>
          <img:threshold_factor/>
        </img:Hot_Pixel>
        <img:Saturated_Pixel>
          <img:pixel_count/>
          <img:threshold_value/>
        </img:Saturated_Pixel>
        <img:Nonlinear_Pixel>
          <img:pixel_count/>
          <img:threshold_value/>
        </img:Nonlinear_Pixel>
      </img:Data_Quality>
      <img:Detector>
        <img:first_line/>
        <img:first_sample/>
        <img:lines/>
        <img:samples/>
        <img:detector_to_image_rotation/>
        <img:detector_to_image_flip/>
        <img:erase_count/>
        <img:frame_count/>
        <img:readout_rate/>
        <img:gain_count/>
        <img:gain_db/>
        <img:gain_mode_id/>
        <img:gain_number/>
        <img:analog_offset/>
        <img:analog_offset_count/>
        <img:analog_offset_percent/>
        <img:analog_offset_voltage/>
        <img:bad_pixel_replacement_flag/>
        <img:bad_pixel_replacement_table_id/>
        <img:instrument_idle_timeout/>
        <img:early_image_return/>
        <img:parameter_table_id/>
        <img:ISO>
          <img:iso_number/>
          <img:iso_mode_id/>
        </img:ISO>
        <img:Special_Point>
          <img:name/>
          <img:description/>
          <img:special_line/>
          <img:special_sample/>
        </img:Special_Point>
        <img:Shutter>
          <img:shutter_type/>
          <img:readout_direction_pixel/>
          <img:readout_direction_line/>
          <img:pixel_readout_time/>
          <img:line_readout_time/>
          <img:frame_readout_time/>
        </img:Shutter>
        <img:Internal_Reference>
        </img:Internal_Reference>
      </img:Detector>
      <img:Downsampling>
        <img:active_flag/>
        <img:processing_venue/>
        <img:processing_algorithm/>
        <img:sequence_number/>
        <img:Pixel_Averaging_Dimensions>
          <img:height_pixels/>
          <img:width_pixels/>
        </img:Pixel_Averaging_Dimensions>
      </img:Downsampling>
      <img:Exposure>
        <img:exposure_count/>
        <img:exposure_duration/>
        <img:exposure_duration_count/>
        <img:exposure_type/>
        <img:exposure_scale_factor/>
        <img:exposure_coadd_count/>
        <img:exposure_readout_count/>
        <img:Autoexposure>
          <img:auto_exposure_alpha/>
          <img:active_flag/>
          <img:auto_exposure_data_cut/>
          <img:processing_venue/>
          <img:auto_exposure_percent/>
          <img:processing_algorithm/>
          <img:auto_exposure_pixel_fraction/>
          <img:sequence_number/>
          <img:auto_exposure_lower_threshold/>
          <img:auto_exposure_lower_limit/>
          <img:auto_exposure_max_delta/>
          <img:auto_exposure_roi_first_line/>
          <img:auto_exposure_roi_first_sample/>
          <img:auto_exposure_roi_lines/>
          <img:auto_exposure_roi_samples/>
          <img:auto_expose_target_dn/>
          <img:auto_exposure_target_msv/>
          <img:auto_exposure_upper_threshold/>
          <img:auto_exposure_upper_limit/>
          <img:max_auto_exposure_iteration_count/>
          <img:exposure_table/>
          <img:exposure_table_update_flag/>
          <img:valid_maximum_pixel/>
          <img:valid_minimum_pixel/>
        </img:Autoexposure>
      </img:Exposure>
      <img:Flat_Field_Correction>
        <img:active_flag/>
        <img:processing_venue/>
        <img:processing_algorithm/>
        <img:sequence_number/>
        <img:Radial_Flat_Field_Function>
          <img:x_center/>
          <img:y_center/>
          <img:r0/>
          <img:r1/>
          <img:r2/>
          <img:r3/>
          <img:Flat_Field_File>
            <img:description/>
            <img:name/>
            <img:Internal_Reference>
            </img:Internal_Reference>
            <img:External_Reference>
            </img:External_Reference>
          </img:Flat_Field_File>
        </img:Radial_Flat_Field_Function>
        <img:Flat_Field_File>
        </img:Flat_Field_File>
      </img:Flat_Field_Correction>
      <img:Focus>
        <img:focus_mode/>
        <img:focus_position/>
        <img:focus_position_count/>
        <img:autofocus_step_size/>
        <img:autofocus_step_count/>
        <img:focus_distance/>
        <img:focus_initialization_flag/>
        <img:minimum_focus_distance/>
        <img:best_focus_distance/>
        <img:maximum_focus_distance/>
      </img:Focus>
      <img:Focus_Stack>
        <img:active_flag/>
        <img:focus_stack_flag/>
        <img:processing_venue/>
        <img:frame_count/>
        <img:processing_algorithm/>
        <img:frame_index/>
        <img:sequence_number/>
        <img:focus_merge_blending_flag/>
        <img:focus_merge_registration_flag/>
        <img:delta_focus_count/>
      </img:Focus_Stack>
      <img:Frame>
        <img:frame_id/>
        <img:frame_type_name/>
        <img:product_flag/>
        <img:observation_number/>
      </img:Frame>
      <img:High_Dynamic_Range>
        <img:active_flag/>
        <img:processing_venue/>
        <img:hdr_acquisition_mode/>
        <img:processing_algorithm/>
        <img:hdr_frame_count/>
        <img:sequence_number/>
        <img:hdr_clipping_threshold/>
        <img:High_Dynamic_Range_Exposure>
          <img:exposure_duration/>
          <img:exposure_duration_count/>
          <img:exposure_time_delta/>
          <img:Internal_Reference>
          </img:Internal_Reference>
        </img:High_Dynamic_Range_Exposure>
      </img:High_Dynamic_Range>
      <img:Histogram>
        <img:download_priority/>
        <img:product_flag/>
      </img:Histogram>
      <img:Illumination>
        <img:name/>
        <img:illumination_mode/>
        <img:LED_Illumination_Source>
          <img:name/>
          <img:description/>
          <img:illumination_state/>
          <img:illumination_wavelength/>
        </img:LED_Illumination_Source>
      </img:Illumination>
      <img:Image_Filter>
        <img:active_flag/>
        <img:processing_venue/>
        <img:filter_window_line/>
        <img:processing_algorithm/>
        <img:filter_window_sample/>
        <img:sequence_number/>
        <img:max_filter_window_line/>
        <img:max_filter_window_sample/>
        <img:min_filter_window_line/>
        <img:min_filter_window_sample/>
      </img:Image_Filter>
      <img:Image_Mask>
        <img:active_flag/>
        <img:horizon_mask_elevation/>
        <img:processing_venue/>
        <img:processing_algorithm/>
        <img:sequence_number/>
        <img:Image_Mask_File>
          <img:description/>
          <img:name/>
          <img:mask_type/>
          <img:horizon_mask_elevation/>
          <img:mask_transparent_value/>
          <img:Internal_Reference>
          </img:Internal_Reference>
          <img:External_Reference>
          </img:External_Reference>
        </img:Image_Mask_File>
      </img:Image_Mask>
      <img:Onboard_Compression>
        <img:onboard_compression_class/>
        <img:onboard_compression_mode/>
        <img:onboard_compression_type/>
        <img:onboard_compression_rate/>
        <img:onboard_compression_ratio/>
        <img:onboard_compression_quality/>
        <img:onboard_compression_venue/>
        <img:deferred_flag/>
        <img:error_pixel_count/>
        <img:ICER_Parameters>
          <img:wavelet_filter/>
          <img:icer_quality/>
          <img:decomposition_stages/>
          <img:segment_count/>
          <img:Image_Compression_Segment>
            <img:segment_number/>
            <img:first_line/>
            <img:first_sample/>
            <img:lines/>
            <img:samples/>
            <img:segment_quality/>
            <img:segment_status/>
            <img:segment_corrupted_flag/>
            <img:missing_pixel_count/>
          </img:Image_Compression_Segment>
        </img:ICER_Parameters>
        <img:LOCO_Parameters>
          <img:wavelet_filter/>
          <img:missing_pixel_count/>
          <img:segment_count/>
          <img:Image_Compression_Segment>
          </img:Image_Compression_Segment>
        </img:LOCO_Parameters>
        <img:JPEG_Parameters>
          <img:color_subsampling_mode/>
          <img:jpeg_quality/>
          <img:jpeg_parameter/>
          <img:Image_Compression_Segment>
          </img:Image_Compression_Segment>
        </img:JPEG_Parameters>
        <img:JPEG_Progressive_Parameters>
          <img:color_subsampling_mode/>
          <img:jpeg_quality/>
          <img:progressive_stage/>
          <img:jpeg_parameter/>
          <img:Image_Compression_Segment>
          </img:Image_Compression_Segment>
        </img:JPEG_Progressive_Parameters>
        <img:StarPixel_Flexible_Parameters>
          <img:starpixel_initial_subsampling_interval/>
          <img:starpixel_degradation/>
          <img:Image_Compression_Segment>
          </img:Image_Compression_Segment>
        </img:StarPixel_Flexible_Parameters>
        <img:StarPixel_Lossless_Parameters>
          <img:starpixel_initial_subsampling_interval/>
          <img:Image_Compression_Segment>
          </img:Image_Compression_Segment>
        </img:StarPixel_Lossless_Parameters>
      </img:Onboard_Compression>
      <img:Optical_Filter>
        <img:filter_name/>
        <img:filter_id/>
        <img:filter_number/>
        <img:filter_position_count/>
        <img:bandwidth/>
        <img:center_filter_wavelength/>
        <img:array_band_number/>
        <img:comment/>
        <img:Local_Internal_Reference>
        </img:Local_Internal_Reference>
      </img:Optical_Filter>
      <img:Optical_Properties>
        <img:focal_length/>
        <img:f_number/>
        <img:zoom_position/>
      </img:Optical_Properties>
      <img:Pointing_Correction>
        <img:Pointing_Correction_File>
          <img:description/>
          <img:name/>
          <img:Internal_Reference>
          </img:Internal_Reference>
          <img:External_Reference>
          </img:External_Reference>
        </img:Pointing_Correction_File>
        <img:Pointing_Correction_Image>
          <img:pointing_model_name/>
          <img:pointing_model_solution_id/>
          <img:Pointing_Model_Parameter>
            <img:name/>
            <img:value/>
          </img:Pointing_Model_Parameter>
        </img:Pointing_Correction_Image>
      </img:Pointing_Correction>
      <img:Radiometric_Correction>
        <img:active_flag/>
        <img:radiometric_type/>
        <img:processing_venue/>
        <img:radiometric_zenith_scaling_factor/>
        <img:processing_algorithm/>
        <img:responsivity_r/>
        <img:sequence_number/>
        <img:responsivity_g/>
        <img:responsivity_b/>
        <img:responsivity_pan/>
        <img:responsivity_std/>
        <img:atmospheric_opacity/>
        <img:atmospheric_opacity_reference/>
        <img:effective_wavelength/>
        <img:iof_conversion_coefficient/>
        <img:iof_conversion_correction/>
        <img:iof_conversion_coefficient_std/>
        <img:inband_fsun/>
        <img:comment/>
      </img:Radiometric_Correction>
      <img:Reference_Pixel>
        <img:download_priority/>
        <img:product_flag/>
        <img:Onboard_Compression>
        </img:Onboard_Compression>
      </img:Reference_Pixel>
      <img:Row_Sum>
        <img:download_priority/>
        <img:product_flag/>
      </img:Row_Sum>
      <img:Sampling>
        <img:crosstrack_summing/>
        <img:downtrack_summing/>
        <img:missing_pixel_count/>
        <img:original_sample_bits/>
        <img:sample_bits/>
        <img:sample_bit_mask/>
        <img:sampling_factor/>
        <img:saturated_pixel_count/>
        <img:valid_pixel_count/>
        <img:Companding>
          <img:companding_state/>
          <img:active_flag/>
          <img:early_scaling/>
          <img:processing_venue/>
          <img:processing_algorithm/>
          <img:sequence_number/>
          <img:Companding_File>
            <img:description/>
            <img:name/>
            <img:Internal_Reference>
            </img:Internal_Reference>
            <img:External_Reference>
            </img:External_Reference>
          </img:Companding_File>
          <img:Companding_Table>
            <img:description/>
            <img:name/>
            <img:Companding_Table_Mapping>
              <img:input_dn_min/>
              <img:input_dn_max/>
              <img:output_dn/>
            </img:Companding_Table_Mapping>
            <img:Internal_Reference>
            </img:Internal_Reference>
            <img:External_Reference>
            </img:External_Reference>
          </img:Companding_Table>
        </img:Companding>
      </img:Sampling>
      <img:Shutter_Subtraction>
        <img:active_flag/>
        <img:shutter_subtraction_mode/>
        <img:processing_venue/>
        <img:exposure_duration_threshold_count/>
        <img:processing_algorithm/>
        <img:sequence_number/>
      </img:Shutter_Subtraction>
      <img:Spatial_Filter>
        <img:active_flag/>
        <img:processing_venue/>
        <img:filter_window_line/>
        <img:processing_algorithm/>
        <img:filter_window_sample/>
        <img:sequence_number/>
        <img:max_filter_window_line/>
        <img:max_filter_window_sample/>
        <img:min_filter_window_line/>
        <img:min_filter_window_sample/>
      </img:Spatial_Filter>
      <img:Subframe>
        <img:first_line/>
        <img:first_sample/>
        <img:lines/>
        <img:samples/>
        <img:line_fov/>
        <img:sample_fov/>
        <img:name/>
        <img:description/>
        <img:subframe_type/>
      </img:Subframe>
      <img:Thumbnail>
        <img:download_priority/>
        <img:frame_id/>
        <img:frame_type_name/>
        <img:product_flag/>
        <img:Onboard_Compression>
        </img:Onboard_Compression>
        <img:Sampling>
        </img:Sampling>
        <img:Subframe>
        </img:Subframe>
      </img:Thumbnail>
      <img:Tiling>
        <img:description/>
        <img:num_line_tiles/>
        <img:num_sample_tiles/>
        <img:tile_count/>
        <img:tile_lines/>
        <img:tile_samples/>
        <img:tile_type/>
        <img:tile_venue/>
        <img:Tile>
          <img:tile_number/>
          <img:tile_num_bands/>
          <img:tile_upsample_method/>
          <img:Internal_Reference>
          </img:Internal_Reference>
          <img:Local_Internal_Reference>
          </img:Local_Internal_Reference>
          <img:External_Reference>
          </img:External_Reference>
          <img:Pixel_Averaging_Dimensions>
          </img:Pixel_Averaging_Dimensions>
          <img:Subframe>
          </img:Subframe>
        </img:Tile>
      </img:Tiling>
      <img:Video>
        <img:video_flag/>
        <img:frame_count/>
        <img:interframe_delay/>
        <img:pre_video_delay/>
        <img:frame_rate/>
        <img:frame_interval/>
        <img:frame_index/>
        <img:frame_source_id/>
        <img:gop_frame_index/>
        <img:gop_frame_count/>
        <img:gop_start_index/>
        <img:Internal_Reference>
        </img:Internal_Reference>
        <img:External_Reference>
        </img:External_Reference>
      </img:Video>
      <img:White_Balance>
        <img:active_flag/>
        <img:white_balance_color_temp/>
        <img:processing_venue/>
        <img:processing_algorithm/>
        <img:sequence_number/>
      </img:White_Balance>
      <img:Instrument_State>
        <img:Device_Component_States>
          <img:Device_Component_State>
            <img:device_state/>
            <img:device_name/>
            <img:device_id/>
            <img:sequence_number/>
          </img:Device_Component_State>
        </img:Device_Component_States>
        <img:Device_Currents>
          <img:Device_Current>
            <img:current_value/>
            <img:device_name/>
            <img:device_id/>
            <img:sequence_number/>
          </img:Device_Current>
        </img:Device_Currents>
        <img:Device_Motor_Counts>
          <img:Device_Motor_Count>
            <img:motor_count/>
            <img:device_name/>
            <img:device_id/>
            <img:sequence_number/>
          </img:Device_Motor_Count>
        </img:Device_Motor_Counts>
        <img:Device_Temperatures>
          <img:Device_Temperature>
            <img:raw_count/>
            <img:device_name/>
            <img:device_id/>
            <img:sequence_number/>
            <img:temperature_value/>
            <img:temperature_status/>
          </img:Device_Temperature>
        </img:Device_Temperatures>
        <img:Device_Voltages>
          <img:Device_Voltage>
            <img:voltage_value/>
            <img:device_name/>
            <img:device_id/>
            <img:sequence_number/>
          </img:Device_Voltage>
        </img:Device_Voltages>
      </img:Instrument_State>
      <img:Commanded_Parameters>
        <img:description/>
        <img:Brightness_Correction>
        </img:Brightness_Correction>
        <img:Col_Sum>
        </img:Col_Sum>
        <img:Color_Filter_Array>
        </img:Color_Filter_Array>
        <img:Color_Processing>
        </img:Color_Processing>
        <img:Dark_Current_Correction>
        </img:Dark_Current_Correction>
        <img:Data_Quality>
        </img:Data_Quality>
        <img:Detector>
        </img:Detector>
        <img:Downsampling>
        </img:Downsampling>
        <img:Exposure>
        </img:Exposure>
        <img:Flat_Field_Correction>
        </img:Flat_Field_Correction>
        <img:Focus>
        </img:Focus>
        <img:Focus_Stack>
        </img:Focus_Stack>
        <img:Frame>
        </img:Frame>
        <img:High_Dynamic_Range>
        </img:High_Dynamic_Range>
        <img:Histogram>
        </img:Histogram>
        <img:Illumination>
        </img:Illumination>
        <img:Image_Filter>
        </img:Image_Filter>
        <img:Image_Mask>
        </img:Image_Mask>
        <img:Onboard_Compression>
        </img:Onboard_Compression>
        <img:Optical_Filter>
        </img:Optical_Filter>
        <img:Optical_Properties>
        </img:Optical_Properties>
        <img:Pointing_Correction>
        </img:Pointing_Correction>
        <img:Radiometric_Correction>
        </img:Radiometric_Correction>
        <img:Reference_Pixel>
        </img:Reference_Pixel>
        <img:Row_Sum>
        </img:Row_Sum>
        <img:Sampling>
        </img:Sampling>
        <img:Shutter_Subtraction>
        </img:Shutter_Subtraction>
        <img:Spatial_Filter>
        </img:Spatial_Filter>
        <img:Subframe>
        </img:Subframe>
        <img:Thumbnail>
        </img:Thumbnail>
        <img:Tiling>
        </img:Tiling>
        <img:Video>
        </img:Video>
        <img:White_Balance>
        </img:White_Balance>
      </img:Commanded_Parameters>
    </img:Imaging>
      <img:sequence_number/>
      <img:name/>
      <img:id/>
      <img:value_number/>
      <img:value_string/>
  </Discipline_Area>
  ...
</Observation_Area>
```  
  
The namespace for the Imaging Discipline Data Dictionary is http://pds.nasa.gov/pds4/img/v1, abbreviated "img:".  
  
# Organization of Classes and Attributes  
  
## Class Organization  
Below is a structured list showing the organization of classes, ordered by appearance in the PDS4 label. Each class name is linked to its complete definition in the [Definitions](#definitions) section.  
- [Correction_Parameter](#correction_parameter)  
- [Data_Processing](#data_processing)  
- [Data_Processing_File](#data_processing_file)  
  - [Internal_Reference](#internal_reference)  
  - [External_Reference](#external_reference)  
- [Device_Parameters](#device_parameters)  
- [Imaging](#imaging)  
  - [Local_Internal_Reference](#local_internal_reference)  
  - [Brightness_Correction](#brightness_correction)  
    - [Brightness_Correction_File](#brightness_correction_file)  
      - [Internal_Reference](#internal_reference)  
      - [External_Reference](#external_reference)  
    - [Brightness_Correction_Image](#brightness_correction_image)  
      - [Internal_Reference](#internal_reference)  
      - [Brightness_Correction_Linear](#brightness_correction_linear)  
      - [Brightness_Correction_HSI_Linear](#brightness_correction_hsi_linear)  
  - [Col_Sum](#col_sum)  
  - [Color_Filter_Array](#color_filter_array)  
  - [Color_Processing](#color_processing)  
    - [Onboard_Responsivity](#onboard_responsivity)  
    - [Onboard_Color_Matrix](#onboard_color_matrix)  
  - [Dark_Current_Correction](#dark_current_correction)  
  - [Data_Quality](#data_quality)  
    - [Hot_Pixel](#hot_pixel)  
    - [Saturated_Pixel](#saturated_pixel)  
    - [Nonlinear_Pixel](#nonlinear_pixel)  
  - [Detector](#detector)  
    - [ISO](#iso)  
    - [Special_Point](#special_point)  
    - [Shutter](#shutter)  
    - [Internal_Reference](#internal_reference)  
  - [Downsampling](#downsampling)  
    - [Pixel_Averaging_Dimensions](#pixel_averaging_dimensions)  
  - [Exposure](#exposure)  
    - [Autoexposure](#autoexposure)  
  - [Flat_Field_Correction](#flat_field_correction)  
    - [Radial_Flat_Field_Function](#radial_flat_field_function)  
      - [Flat_Field_File](#flat_field_file)  
        - [Internal_Reference](#internal_reference)  
        - [External_Reference](#external_reference)  
    - [Flat_Field_File](#flat_field_file)  
  - [Focus](#focus)  
  - [Focus_Stack](#focus_stack)  
  - [Frame](#frame)  
  - [High_Dynamic_Range](#high_dynamic_range)  
    - [High_Dynamic_Range_Exposure](#high_dynamic_range_exposure)  
      - [Internal_Reference](#internal_reference)  
  - [Histogram](#histogram)  
  - [Illumination](#illumination)  
    - [LED_Illumination_Source](#led_illumination_source)  
  - [Image_Filter](#image_filter)  
  - [Image_Mask](#image_mask)  
    - [Image_Mask_File](#image_mask_file)  
      - [Internal_Reference](#internal_reference)  
      - [External_Reference](#external_reference)  
  - [Onboard_Compression](#onboard_compression)  
    - [ICER_Parameters](#icer_parameters)  
      - [Image_Compression_Segment](#image_compression_segment)  
    - [LOCO_Parameters](#loco_parameters)  
      - [Image_Compression_Segment](#image_compression_segment)  
    - [JPEG_Parameters](#jpeg_parameters)  
      - [Image_Compression_Segment](#image_compression_segment)  
    - [JPEG_Progressive_Parameters](#jpeg_progressive_parameters)  
      - [Image_Compression_Segment](#image_compression_segment)  
    - [StarPixel_Flexible_Parameters](#starpixel_flexible_parameters)  
      - [Image_Compression_Segment](#image_compression_segment)  
    - [StarPixel_Lossless_Parameters](#starpixel_lossless_parameters)  
      - [Image_Compression_Segment](#image_compression_segment)  
  - [Optical_Filter](#optical_filter)  
    - [Local_Internal_Reference](#local_internal_reference)  
  - [Optical_Properties](#optical_properties)  
  - [Pointing_Correction](#pointing_correction)  
    - [Pointing_Correction_File](#pointing_correction_file)  
      - [Internal_Reference](#internal_reference)  
      - [External_Reference](#external_reference)  
    - [Pointing_Correction_Image](#pointing_correction_image)  
      - [Pointing_Model_Parameter](#pointing_model_parameter)  
  - [Radiometric_Correction](#radiometric_correction)  
  - [Reference_Pixel](#reference_pixel)  
    - [Onboard_Compression](#onboard_compression)  
  - [Row_Sum](#row_sum)  
  - [Sampling](#sampling)  
    - [Companding](#companding)  
      - [Companding_File](#companding_file)  
        - [Internal_Reference](#internal_reference)  
        - [External_Reference](#external_reference)  
      - [Companding_Table](#companding_table)  
        - [Companding_Table_Mapping](#companding_table_mapping)  
        - [Internal_Reference](#internal_reference)  
        - [External_Reference](#external_reference)  
  - [Shutter_Subtraction](#shutter_subtraction)  
  - [Spatial_Filter](#spatial_filter)  
  - [Subframe](#subframe)  
  - [Thumbnail](#thumbnail)  
    - [Onboard_Compression](#onboard_compression)  
    - [Sampling](#sampling)  
    - [Subframe](#subframe)  
  - [Tiling](#tiling)  
    - [Tile](#tile)  
      - [Internal_Reference](#internal_reference)  
      - [Local_Internal_Reference](#local_internal_reference)  
      - [External_Reference](#external_reference)  
      - [Pixel_Averaging_Dimensions](#pixel_averaging_dimensions)  
      - [Subframe](#subframe)  
  - [Video](#video)  
    - [Internal_Reference](#internal_reference)  
    - [External_Reference](#external_reference)  
  - [White_Balance](#white_balance)  
  - [Instrument_State](#instrument_state)  
    - [Device_Component_States](#device_component_states)  
      - [Device_Component_State](#device_component_state)  
    - [Device_Currents](#device_currents)  
      - [Device_Current](#device_current)  
    - [Device_Motor_Counts](#device_motor_counts)  
      - [Device_Motor_Count](#device_motor_count)  
    - [Device_Temperatures](#device_temperatures)  
      - [Device_Temperature](#device_temperature)  
    - [Device_Voltages](#device_voltages)  
      - [Device_Voltage](#device_voltage)  
  - [Commanded_Parameters](#commanded_parameters)  
    - [Brightness_Correction](#brightness_correction)  
    - [Col_Sum](#col_sum)  
    - [Color_Filter_Array](#color_filter_array)  
    - [Color_Processing](#color_processing)  
    - [Dark_Current_Correction](#dark_current_correction)  
    - [Data_Quality](#data_quality)  
    - [Detector](#detector)  
    - [Downsampling](#downsampling)  
    - [Exposure](#exposure)  
    - [Flat_Field_Correction](#flat_field_correction)  
    - [Focus](#focus)  
    - [Focus_Stack](#focus_stack)  
    - [Frame](#frame)  
    - [High_Dynamic_Range](#high_dynamic_range)  
    - [Histogram](#histogram)  
    - [Illumination](#illumination)  
    - [Image_Filter](#image_filter)  
    - [Image_Mask](#image_mask)  
    - [Onboard_Compression](#onboard_compression)  
    - [Optical_Filter](#optical_filter)  
    - [Optical_Properties](#optical_properties)  
    - [Pointing_Correction](#pointing_correction)  
    - [Radiometric_Correction](#radiometric_correction)  
    - [Reference_Pixel](#reference_pixel)  
    - [Row_Sum](#row_sum)  
    - [Sampling](#sampling)  
    - [Shutter_Subtraction](#shutter_subtraction)  
    - [Spatial_Filter](#spatial_filter)  
    - [Subframe](#subframe)  
    - [Thumbnail](#thumbnail)  
    - [Tiling](#tiling)  
    - [Video](#video)  
    - [White_Balance](#white_balance)  
- [List_Index_No_Units_Imaging](#list_index_no_units_imaging--abstract)  `*abstract*`  
  
## Attributes by Class  
The attributes immediately under each class (if any) are listed below. Both classes and attributes are ordered by appearance in the PDS4 label; however, each class is listed only once, even if that class can appear in more than one place in a PDS4 label. Each class and attribute name is linked to its complete definition in the [Definitions](#definitions) section.  
  
### [Correction_Parameter](#correction_parameter) (attribute list)  
- [sequence_number](#sequence_number)  
- [name](#name)  
- [id](#id)  
- [value_number](#value_number)  
- [value_string](#value_string)  
  
### [Data_Processing](#data_processing) (attribute list)  
- [active_flag](#active_flag)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Data_Processing_File](#data_processing_file) (attribute list)  
- [description](#description)  
- [name](#name)  
  
### [Internal_Reference](#internal_reference) (attribute list)  
  
### [External_Reference](#external_reference) (attribute list)  
  
### [Device_Parameters](#device_parameters) (attribute list)  
- [device_name](#device_name)  
- [device_id](#device_id)  
- [sequence_number](#sequence_number)  
  
### [Imaging](#imaging) (attribute list)  
  
### [Local_Internal_Reference](#local_internal_reference) (attribute list)  
  
### [Brightness_Correction](#brightness_correction) (attribute list)  
- [active_flag](#active_flag)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Brightness_Correction_File](#brightness_correction_file) (attribute list)  
- [description](#description)  
- [name](#name)  
  
### [Brightness_Correction_Image](#brightness_correction_image) (attribute list)  
  
### [Brightness_Correction_Linear](#brightness_correction_linear) (attribute list)  
- [brightness_scale](#brightness_scale)  
- [brightness_offset](#brightness_offset)  
  
### [Brightness_Correction_HSI_Linear](#brightness_correction_hsi_linear) (attribute list)  
- [brightness_scale](#brightness_scale)  
- [brightness_offset](#brightness_offset)  
  
### [Col_Sum](#col_sum) (attribute list)  
- [download_priority](#download_priority)  
- [product_flag](#product_flag)  
  
### [Color_Filter_Array](#color_filter_array) (attribute list)  
- [color_filter_array_type](#color_filter_array_type)  
- [active_flag](#active_flag)  
- [color_filter_array_state](#color_filter_array_state)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Color_Processing](#color_processing) (attribute list)  
- [color_space](#color_space)  
- [active_flag](#active_flag)  
- [color_component](#color_component)  
- [processing_venue](#processing_venue)  
- [illuminant](#illuminant)  
- [processing_algorithm](#processing_algorithm)  
- [encoded_display_gamma](#encoded_display_gamma)  
- [sequence_number](#sequence_number)  
- [color_dn_scaling_method](#color_dn_scaling_method)  
- [color_dn_scaling_factor](#color_dn_scaling_factor)  
  
### [Onboard_Responsivity](#onboard_responsivity) (attribute list)  
- [responsivity_factor_r](#responsivity_factor_r)  
- [responsivity_factor_g](#responsivity_factor_g)  
- [responsivity_factor_b](#responsivity_factor_b)  
  
### [Onboard_Color_Matrix](#onboard_color_matrix) (attribute list)  
- [onboard_R_r](#onboard_r_r)  
- [onboard_R_g](#onboard_r_g)  
- [onboard_R_b](#onboard_r_b)  
- [onboard_G_r](#onboard_g_r)  
- [onboard_G_g](#onboard_g_g)  
- [onboard_G_b](#onboard_g_b)  
- [onboard_B_r](#onboard_b_r)  
- [onboard_B_g](#onboard_b_g)  
- [onboard_B_b](#onboard_b_b)  
  
### [Dark_Current_Correction](#dark_current_correction) (attribute list)  
- [striping_count](#striping_count)  
- [active_flag](#active_flag)  
- [striping_overlap_rows](#striping_overlap_rows)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Data_Quality](#data_quality) (attribute list)  
- [dq_band](#dq_band)  
- [dq_bayer_cell](#dq_bayer_cell)  
- [comment](#comment)  
- [no_signal_count](#no_signal_count)  
- [above_aft_flag](#above_aft_flag)  
- [below_aft_flag](#below_aft_flag)  
- [full_well_limit_flag](#full_well_limit_flag)  
- [data_received](#data_received)  
- [image_corrupt_flag](#image_corrupt_flag)  
- [missing_temperature_flag](#missing_temperature_flag)  
- [out_of_focus_flag](#out_of_focus_flag)  
- [saturated_flag](#saturated_flag)  
- [sequence_terminated_flag](#sequence_terminated_flag)  
- [wrong_filter_flag](#wrong_filter_flag)  
- [wrong_pointing_flag](#wrong_pointing_flag)  
- [wrong_zoom_flag](#wrong_zoom_flag)  
- [zero_value_pixels_flag](#zero_value_pixels_flag)  
  
### [Hot_Pixel](#hot_pixel) (attribute list)  
- [pixel_count](#pixel_count)  
- [threshold_factor](#threshold_factor)  
  
### [Saturated_Pixel](#saturated_pixel) (attribute list)  
- [pixel_count](#pixel_count)  
- [threshold_value](#threshold_value)  
  
### [Nonlinear_Pixel](#nonlinear_pixel) (attribute list)  
- [pixel_count](#pixel_count)  
- [threshold_value](#threshold_value)  
  
### [Detector](#detector) (attribute list)  
- [first_line](#first_line)  
- [first_sample](#first_sample)  
- [lines](#lines)  
- [samples](#samples)  
- [detector_to_image_rotation](#detector_to_image_rotation)  
- [detector_to_image_flip](#detector_to_image_flip)  
- [erase_count](#erase_count)  
- [frame_count](#frame_count)  
- [readout_rate](#readout_rate)  
- [gain_count](#gain_count)  
- [gain_db](#gain_db)  
- [gain_mode_id](#gain_mode_id)  
- [gain_number](#gain_number)  
- [analog_offset](#analog_offset)  
- [analog_offset_count](#analog_offset_count)  
- [analog_offset_percent](#analog_offset_percent)  
- [analog_offset_voltage](#analog_offset_voltage)  
- [bad_pixel_replacement_flag](#bad_pixel_replacement_flag)  
- [bad_pixel_replacement_table_id](#bad_pixel_replacement_table_id)  
- [instrument_idle_timeout](#instrument_idle_timeout)  
- [early_image_return](#early_image_return)  
- [parameter_table_id](#parameter_table_id)  
  
### [ISO](#iso) (attribute list)  
- [iso_number](#iso_number)  
- [iso_mode_id](#iso_mode_id)  
  
### [Special_Point](#special_point) (attribute list)  
- [name](#name)  
- [description](#description)  
- [special_line](#special_line)  
- [special_sample](#special_sample)  
  
### [Shutter](#shutter) (attribute list)  
- [shutter_type](#shutter_type)  
- [readout_direction_pixel](#readout_direction_pixel)  
- [readout_direction_line](#readout_direction_line)  
- [pixel_readout_time](#pixel_readout_time)  
- [line_readout_time](#line_readout_time)  
- [frame_readout_time](#frame_readout_time)  
  
### [Downsampling](#downsampling) (attribute list)  
- [active_flag](#active_flag)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Pixel_Averaging_Dimensions](#pixel_averaging_dimensions) (attribute list)  
- [height_pixels](#height_pixels)  
- [width_pixels](#width_pixels)  
  
### [Exposure](#exposure) (attribute list)  
- [exposure_count](#exposure_count)  
- [exposure_duration](#exposure_duration)  
- [exposure_duration_count](#exposure_duration_count)  
- [exposure_type](#exposure_type)  
- [exposure_scale_factor](#exposure_scale_factor)  
- [exposure_coadd_count](#exposure_coadd_count)  
- [exposure_readout_count](#exposure_readout_count)  
  
### [Autoexposure](#autoexposure) (attribute list)  
- [auto_exposure_alpha](#auto_exposure_alpha)  
- [active_flag](#active_flag)  
- [auto_exposure_data_cut](#auto_exposure_data_cut)  
- [processing_venue](#processing_venue)  
- [auto_exposure_percent](#auto_exposure_percent)  
- [processing_algorithm](#processing_algorithm)  
- [auto_exposure_pixel_fraction](#auto_exposure_pixel_fraction)  
- [sequence_number](#sequence_number)  
- [auto_exposure_lower_threshold](#auto_exposure_lower_threshold)  
- [auto_exposure_lower_limit](#auto_exposure_lower_limit)  
- [auto_exposure_max_delta](#auto_exposure_max_delta)  
- [auto_exposure_roi_first_line](#auto_exposure_roi_first_line)  
- [auto_exposure_roi_first_sample](#auto_exposure_roi_first_sample)  
- [auto_exposure_roi_lines](#auto_exposure_roi_lines)  
- [auto_exposure_roi_samples](#auto_exposure_roi_samples)  
- [auto_expose_target_dn](#auto_expose_target_dn)  
- [auto_exposure_target_msv](#auto_exposure_target_msv)  
- [auto_exposure_upper_threshold](#auto_exposure_upper_threshold)  
- [auto_exposure_upper_limit](#auto_exposure_upper_limit)  
- [max_auto_exposure_iteration_count](#max_auto_exposure_iteration_count)  
- [exposure_table](#exposure_table)  
- [exposure_table_update_flag](#exposure_table_update_flag)  
- [valid_maximum_pixel](#valid_maximum_pixel)  
- [valid_minimum_pixel](#valid_minimum_pixel)  
  
### [Flat_Field_Correction](#flat_field_correction) (attribute list)  
- [active_flag](#active_flag)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Radial_Flat_Field_Function](#radial_flat_field_function) (attribute list)  
- [x_center](#x_center)  
- [y_center](#y_center)  
- [r0](#r0)  
- [r1](#r1)  
- [r2](#r2)  
- [r3](#r3)  
  
### [Flat_Field_File](#flat_field_file) (attribute list)  
- [description](#description)  
- [name](#name)  
  
### [Focus](#focus) (attribute list)  
- [focus_mode](#focus_mode)  
- [focus_position](#focus_position)  
- [focus_position_count](#focus_position_count)  
- [autofocus_step_size](#autofocus_step_size)  
- [autofocus_step_count](#autofocus_step_count)  
- [focus_distance](#focus_distance)  
- [focus_initialization_flag](#focus_initialization_flag)  
- [minimum_focus_distance](#minimum_focus_distance)  
- [best_focus_distance](#best_focus_distance)  
- [maximum_focus_distance](#maximum_focus_distance)  
  
### [Focus_Stack](#focus_stack) (attribute list)  
- [active_flag](#active_flag)  
- [focus_stack_flag](#focus_stack_flag)  
- [processing_venue](#processing_venue)  
- [frame_count](#frame_count)  
- [processing_algorithm](#processing_algorithm)  
- [frame_index](#frame_index)  
- [sequence_number](#sequence_number)  
- [focus_merge_blending_flag](#focus_merge_blending_flag)  
- [focus_merge_registration_flag](#focus_merge_registration_flag)  
- [delta_focus_count](#delta_focus_count)  
  
### [Frame](#frame) (attribute list)  
- [frame_id](#frame_id)  
- [frame_type_name](#frame_type_name)  
- [product_flag](#product_flag)  
- [observation_number](#observation_number)  
  
### [High_Dynamic_Range](#high_dynamic_range) (attribute list)  
- [active_flag](#active_flag)  
- [processing_venue](#processing_venue)  
- [hdr_acquisition_mode](#hdr_acquisition_mode)  
- [processing_algorithm](#processing_algorithm)  
- [hdr_frame_count](#hdr_frame_count)  
- [sequence_number](#sequence_number)  
- [hdr_clipping_threshold](#hdr_clipping_threshold)  
  
### [High_Dynamic_Range_Exposure](#high_dynamic_range_exposure) (attribute list)  
- [exposure_duration](#exposure_duration)  
- [exposure_duration_count](#exposure_duration_count)  
- [exposure_time_delta](#exposure_time_delta)  
  
### [Histogram](#histogram) (attribute list)  
- [download_priority](#download_priority)  
- [product_flag](#product_flag)  
  
### [Illumination](#illumination) (attribute list)  
- [name](#name)  
- [illumination_mode](#illumination_mode)  
  
### [LED_Illumination_Source](#led_illumination_source) (attribute list)  
- [name](#name)  
- [description](#description)  
- [illumination_state](#illumination_state)  
- [illumination_wavelength](#illumination_wavelength)  
  
### [Image_Filter](#image_filter) (attribute list)  
- [active_flag](#active_flag)  
- [processing_venue](#processing_venue)  
- [filter_window_line](#filter_window_line)  
- [processing_algorithm](#processing_algorithm)  
- [filter_window_sample](#filter_window_sample)  
- [sequence_number](#sequence_number)  
- [max_filter_window_line](#max_filter_window_line)  
- [max_filter_window_sample](#max_filter_window_sample)  
- [min_filter_window_line](#min_filter_window_line)  
- [min_filter_window_sample](#min_filter_window_sample)  
  
### [Image_Mask](#image_mask) (attribute list)  
- [active_flag](#active_flag)  
- [horizon_mask_elevation](#horizon_mask_elevation)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Image_Mask_File](#image_mask_file) (attribute list)  
- [description](#description)  
- [name](#name)  
- [mask_type](#mask_type)  
- [horizon_mask_elevation](#horizon_mask_elevation)  
- [mask_transparent_value](#mask_transparent_value)  
  
### [Onboard_Compression](#onboard_compression) (attribute list)  
- [onboard_compression_class](#onboard_compression_class)  
- [onboard_compression_mode](#onboard_compression_mode)  
- [onboard_compression_type](#onboard_compression_type)  
- [onboard_compression_rate](#onboard_compression_rate)  
- [onboard_compression_ratio](#onboard_compression_ratio)  
- [onboard_compression_quality](#onboard_compression_quality)  
- [onboard_compression_venue](#onboard_compression_venue)  
- [deferred_flag](#deferred_flag)  
- [error_pixel_count](#error_pixel_count)  
  
### [ICER_Parameters](#icer_parameters) (attribute list)  
- [wavelet_filter](#wavelet_filter)  
- [icer_quality](#icer_quality)  
- [decomposition_stages](#decomposition_stages)  
- [segment_count](#segment_count)  
  
### [Image_Compression_Segment](#image_compression_segment) (attribute list)  
- [segment_number](#segment_number)  
- [first_line](#first_line)  
- [first_sample](#first_sample)  
- [lines](#lines)  
- [samples](#samples)  
- [segment_quality](#segment_quality)  
- [segment_status](#segment_status)  
- [segment_corrupted_flag](#segment_corrupted_flag)  
- [missing_pixel_count](#missing_pixel_count)  
  
### [LOCO_Parameters](#loco_parameters) (attribute list)  
- [wavelet_filter](#wavelet_filter)  
- [missing_pixel_count](#missing_pixel_count)  
- [segment_count](#segment_count)  
  
### [JPEG_Parameters](#jpeg_parameters) (attribute list)  
- [color_subsampling_mode](#color_subsampling_mode)  
- [jpeg_quality](#jpeg_quality)  
- [jpeg_parameter](#jpeg_parameter)  
  
### [JPEG_Progressive_Parameters](#jpeg_progressive_parameters) (attribute list)  
- [color_subsampling_mode](#color_subsampling_mode)  
- [jpeg_quality](#jpeg_quality)  
- [progressive_stage](#progressive_stage)  
- [jpeg_parameter](#jpeg_parameter)  
  
### [StarPixel_Flexible_Parameters](#starpixel_flexible_parameters) (attribute list)  
- [starpixel_initial_subsampling_interval](#starpixel_initial_subsampling_interval)  
- [starpixel_degradation](#starpixel_degradation)  
  
### [StarPixel_Lossless_Parameters](#starpixel_lossless_parameters) (attribute list)  
- [starpixel_initial_subsampling_interval](#starpixel_initial_subsampling_interval)  
  
### [Optical_Filter](#optical_filter) (attribute list)  
- [filter_name](#filter_name)  
- [filter_id](#filter_id)  
- [filter_number](#filter_number)  
- [filter_position_count](#filter_position_count)  
- [bandwidth](#bandwidth)  
- [center_filter_wavelength](#center_filter_wavelength)  
- [array_band_number](#array_band_number)  
- [comment](#comment)  
  
### [Optical_Properties](#optical_properties) (attribute list)  
- [focal_length](#focal_length)  
- [f_number](#f_number)  
- [zoom_position](#zoom_position)  
  
### [Pointing_Correction](#pointing_correction) (attribute list)  
  
### [Pointing_Correction_File](#pointing_correction_file) (attribute list)  
- [description](#description)  
- [name](#name)  
  
### [Pointing_Correction_Image](#pointing_correction_image) (attribute list)  
- [pointing_model_name](#pointing_model_name)  
- [pointing_model_solution_id](#pointing_model_solution_id)  
  
### [Pointing_Model_Parameter](#pointing_model_parameter) (attribute list)  
- [name](#name)  
- [value](#value)  
  
### [Radiometric_Correction](#radiometric_correction) (attribute list)  
- [active_flag](#active_flag)  
- [radiometric_type](#radiometric_type)  
- [processing_venue](#processing_venue)  
- [radiometric_zenith_scaling_factor](#radiometric_zenith_scaling_factor)  
- [processing_algorithm](#processing_algorithm)  
- [responsivity_r](#responsivity_r)  
- [sequence_number](#sequence_number)  
- [responsivity_g](#responsivity_g)  
- [responsivity_b](#responsivity_b)  
- [responsivity_pan](#responsivity_pan)  
- [responsivity_std](#responsivity_std)  
- [atmospheric_opacity](#atmospheric_opacity)  
- [atmospheric_opacity_reference](#atmospheric_opacity_reference)  
- [effective_wavelength](#effective_wavelength)  
- [iof_conversion_coefficient](#iof_conversion_coefficient)  
- [iof_conversion_correction](#iof_conversion_correction)  
- [iof_conversion_coefficient_std](#iof_conversion_coefficient_std)  
- [inband_fsun](#inband_fsun)  
- [comment](#comment)  
  
### [Reference_Pixel](#reference_pixel) (attribute list)  
- [download_priority](#download_priority)  
- [product_flag](#product_flag)  
  
### [Row_Sum](#row_sum) (attribute list)  
- [download_priority](#download_priority)  
- [product_flag](#product_flag)  
  
### [Sampling](#sampling) (attribute list)  
- [crosstrack_summing](#crosstrack_summing)  
- [downtrack_summing](#downtrack_summing)  
- [missing_pixel_count](#missing_pixel_count)  
- [original_sample_bits](#original_sample_bits)  
- [sample_bits](#sample_bits)  
- [sample_bit_mask](#sample_bit_mask)  
- [sampling_factor](#sampling_factor)  
- [saturated_pixel_count](#saturated_pixel_count)  
- [valid_pixel_count](#valid_pixel_count)  
  
### [Companding](#companding) (attribute list)  
- [companding_state](#companding_state)  
- [active_flag](#active_flag)  
- [early_scaling](#early_scaling)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Companding_File](#companding_file) (attribute list)  
- [description](#description)  
- [name](#name)  
  
### [Companding_Table](#companding_table) (attribute list)  
- [description](#description)  
- [name](#name)  
  
### [Companding_Table_Mapping](#companding_table_mapping) (attribute list)  
- [input_dn_min](#input_dn_min)  
- [input_dn_max](#input_dn_max)  
- [output_dn](#output_dn)  
  
### [Shutter_Subtraction](#shutter_subtraction) (attribute list)  
- [active_flag](#active_flag)  
- [shutter_subtraction_mode](#shutter_subtraction_mode)  
- [processing_venue](#processing_venue)  
- [exposure_duration_threshold_count](#exposure_duration_threshold_count)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Spatial_Filter](#spatial_filter) (attribute list)  
- [active_flag](#active_flag)  
- [processing_venue](#processing_venue)  
- [filter_window_line](#filter_window_line)  
- [processing_algorithm](#processing_algorithm)  
- [filter_window_sample](#filter_window_sample)  
- [sequence_number](#sequence_number)  
- [max_filter_window_line](#max_filter_window_line)  
- [max_filter_window_sample](#max_filter_window_sample)  
- [min_filter_window_line](#min_filter_window_line)  
- [min_filter_window_sample](#min_filter_window_sample)  
  
### [Subframe](#subframe) (attribute list)  
- [first_line](#first_line)  
- [first_sample](#first_sample)  
- [lines](#lines)  
- [samples](#samples)  
- [line_fov](#line_fov)  
- [sample_fov](#sample_fov)  
- [name](#name)  
- [description](#description)  
- [subframe_type](#subframe_type)  
  
### [Thumbnail](#thumbnail) (attribute list)  
- [download_priority](#download_priority)  
- [frame_id](#frame_id)  
- [frame_type_name](#frame_type_name)  
- [product_flag](#product_flag)  
  
### [Tiling](#tiling) (attribute list)  
- [description](#description)  
- [num_line_tiles](#num_line_tiles)  
- [num_sample_tiles](#num_sample_tiles)  
- [tile_count](#tile_count)  
- [tile_lines](#tile_lines)  
- [tile_samples](#tile_samples)  
- [tile_type](#tile_type)  
- [tile_venue](#tile_venue)  
  
### [Tile](#tile) (attribute list)  
- [tile_number](#tile_number)  
- [tile_num_bands](#tile_num_bands)  
- [tile_upsample_method](#tile_upsample_method)  
  
### [Video](#video) (attribute list)  
- [video_flag](#video_flag)  
- [frame_count](#frame_count)  
- [interframe_delay](#interframe_delay)  
- [pre_video_delay](#pre_video_delay)  
- [frame_rate](#frame_rate)  
- [frame_interval](#frame_interval)  
- [frame_index](#frame_index)  
- [frame_source_id](#frame_source_id)  
- [gop_frame_index](#gop_frame_index)  
- [gop_frame_count](#gop_frame_count)  
- [gop_start_index](#gop_start_index)  
  
### [White_Balance](#white_balance) (attribute list)  
- [active_flag](#active_flag)  
- [white_balance_color_temp](#white_balance_color_temp)  
- [processing_venue](#processing_venue)  
- [processing_algorithm](#processing_algorithm)  
- [sequence_number](#sequence_number)  
  
### [Instrument_State](#instrument_state) (attribute list)  
  
### [Device_Component_States](#device_component_states) (attribute list)  
  
### [Device_Component_State](#device_component_state) (attribute list)  
- [device_state](#device_state)  
- [device_name](#device_name)  
- [device_id](#device_id)  
- [sequence_number](#sequence_number)  
  
### [Device_Currents](#device_currents) (attribute list)  
  
### [Device_Current](#device_current) (attribute list)  
- [current_value](#current_value)  
- [device_name](#device_name)  
- [device_id](#device_id)  
- [sequence_number](#sequence_number)  
  
### [Device_Motor_Counts](#device_motor_counts) (attribute list)  
  
### [Device_Motor_Count](#device_motor_count) (attribute list)  
- [motor_count](#motor_count)  
- [device_name](#device_name)  
- [device_id](#device_id)  
- [sequence_number](#sequence_number)  
  
### [Device_Temperatures](#device_temperatures) (attribute list)  
  
### [Device_Temperature](#device_temperature) (attribute list)  
- [raw_count](#raw_count)  
- [device_name](#device_name)  
- [device_id](#device_id)  
- [sequence_number](#sequence_number)  
- [temperature_value](#temperature_value)  
- [temperature_status](#temperature_status)  
  
### [Device_Voltages](#device_voltages) (attribute list)  
  
### [Device_Voltage](#device_voltage) (attribute list)  
- [voltage_value](#voltage_value)  
- [device_name](#device_name)  
- [device_id](#device_id)  
- [sequence_number](#sequence_number)  
  
### [Commanded_Parameters](#commanded_parameters) (attribute list)  
- [description](#description)  
  
### [List_Index_No_Units_Imaging](#list_index_no_units_imaging--abstract) (attribute list)  `*abstract*`  
- [sequence_number](#sequence_number)  
- [name](#name)  
- [id](#id)  
- [value_number](#value_number)  
- [value_string](#value_string)  
  
# Definitions  
  
## Classes (in alphabetical order)  
  
### Autoexposure  
The Autoexposure class contains attributes used to identify or describe the algorithm used to automatically calculate the proper exposure time. This is generally based on some kind of histogram analysis. The specific autoexposure algorithm used is defined in the processing_algorithm attribute, and the specific set of attributes needed to describe it will vary based on the algorithm. Examples of autoexposure algorithms include "Maki 2003" used on MER, MSL ECAMs, M2020 ECAMS; "Maurice 2012" used on MSL ChemCam; "Smith 1997" used on Mars Pathfinder Imager.  
- [go to attribute list](#autoexposure-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Brightness_Correction  
The Brightness_Correction class describes brightness corrections that were applied to an image or mosaic. Brightness correction is the process of adjusting the DN values of adjacent frames in a mosaic so they match visually. It may also involve contrast or vignetting adjustments. The result may no longer be radiometrically calibrated due to the adjustments. The processing_algorithm child of Brightness_Correction describes the type of brightness correction, and should correspond to the classes within Brightness_Correction_Image. If the algorithm is "MIXED", multiple algorithms were used, in which case the specific information in each Brightness_Correction_Image must be used.  
- [go to attribute list](#brightness_correction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Brightness_Correction_File  
The Brightness_Correction_File identifies a file containing brightness correction information. The project SIS should define the format of this file. Correction information may appear in the file, in instances of the Brightness_Correction_Image class, or both (if both, they should be consistent).  
- [go to attribute list](#brightness_correction_file-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Brightness_Correction_HSI_Linear  
The Brightness_Correction_HSI_Linear class works just like Brightness_Correction_Linear, except that the color image is first converted to HSI (Hue, Saturation, Intensity) space, the correction is applied only to Intensity, and then the result is converted back to RGB space.  
- [go to attribute list](#brightness_correction_hsi_linear-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Brightness_Correction_Image  
The Brighness_Correction_Image class describes the brightness correction that was applied to a single image, whether alone or part of a mosaic. The image this correction applies to may be identified via the enclosed Internal_Reference, or via the order in which the Brightness_Correction_Image objects appear (which matches the order given in Input_Product_List).  
- [go to attribute list](#brightness_correction_image-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Brightness_Correction_Linear  
The Brightness_Correction_Linear class describes a simple linear brightness correction, with an additive (brightness_offset) and multiplicative (brightness_scale) factor applied. The result is: output = input * brightness_scale + brightness_offset. If there are multiple bands, the same correction is applied to each band.  
- [go to attribute list](#brightness_correction_linear-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Col_Sum  
Describes a Column Summation product, which is a single row containing the sum of all pixels in each column of the image.  
- [go to attribute list](#col_sum-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Color_Filter_Array  
The Color_Filter_Array class describes whether or not an image was acquired using a Color Filter Array (CFA) and if so, whether and how the CFA pattern was removed. A CFA is a method for making color images using one exposure on a single sensor plane, where microfilters of different wavelengths are put in front of pixels in a specific pattern. The most common pattern is the Bayer pattern, which has a red, blue, and two green pixels in every 2x2 pixel square. Although generally used for RGB color, CFA filters can be of any number and wavelength (see color_filter_array_type).  
- [go to attribute list](#color_filter_array-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Color_Processing  
The Color_Processing class contains parameters describing color correction or processing and how the image is represented in color.  
- [go to attribute list](#color_processing-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Commanded_Parameters  
The Commanded_Parameters class contains attributes used to identify or describe the commands sent to a spacecraft to perform one or more actions resulting in the acquisition of the current data product. These are distinct from similar values in the root Imaging class which indicate the state of the image as acquired.  
- [go to attribute list](#commanded_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Companding  
 The Companding class describes whether or not data is or has had its bit depth reduced (for example conversion from 12 to 8 bits via a lookup table or bit scaling), the venue where it occurred (Software or Hardware), and the method used to complete the companding. The processing_algorithm attribute specifies how data was companded. Generally this will either be via a lookup table (such as a square root encoding), or by shifting bits to preserve the high order bits and discard the low order bits. The value of this keyword is mission specific but there are recommended values that should apply across missions when possible: NONE - no scaling. LUTn - use the numbered lookup table. Lookup tables are defined in the mission SIS. It is preferred for "n" to be a number but it could be a name, for example LUT_MMM_3 to indicate LUT 3 for the MMM instruments (on MSL). MSB_BITn - Shift to make bit "n" the most significant. Bits start numbering at 0 so MSB_BIT7 means no shift for a 12->8 bit companding, while MSB_BIT11 means to shift right 4 bits for a 12->8 bit companding. AUTOSHIFT - Data should be shifted to preserve the highest value. This value should only appear in a command echo; one of the MSB_BITn values should be used in downlinked data to specify what the actual shift was.  
- [go to attribute list](#companding-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Companding_File  
The Companding _File class specifies the file containing the decompanding (inverse LUT) table used to process the data.  
- [go to attribute list](#companding_file-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Companding_Table  
The Companding_Table class specifies the look up table used to compand the data.  
- [go to attribute list](#companding_table-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Companding_Table_Mapping  
The Companding_Table_Mapping class specifies the mapping between the input DN range and the output DN as the data are companded.  
- [go to attribute list](#companding_table_mapping-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Correction_Parameter  
 The Correction_Parameter class specifies identifier(s) and value for a data correction parameter applicable to the parent class.  
- [go to attribute list](#correction_parameter-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Dark_Current_Correction  
Specifies how dark current removal was performed on this image.  
- [go to attribute list](#dark_current_correction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Data_Processing  
The Data_Processing class contains attributes describing how processing and/or calibration was performed on a data product. It is not intended to be used on its own; rather it is intended to be extended by classes specific to a particular type of processing, such as Shutter_Subtraction, Flat_Field_Correction, Companding, etc. The attributes of this class thus become attributes of the extension class.  
- [go to attribute list](#data_processing-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Data_Processing_File  
The Data_Processing_File class contain attributes which identify a file containing calibration data that was applied to the science data. It is not intended to be used on its own; rather it is intended to be extended by classes specific to a particular type of file, such as Flat_Field_File. Note that the "name" attribute is the name of the file; this attribute should only be used if the file is either not included in an archive, or if the delivery status is unknown by the data provider. The External_Reference or Internal_Reference class should be used instead of name if at all possible.  
- [go to attribute list](#data_processing_file-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Data_Quality  
The Data_Quality class contain attributes which identify quality issues in the observation including saturated pixels, hot pixels, nonlinear pixels and flags for listing states for example the observation was out of focus, the pointing was incorrect, the defined zoomed was not achieved, and other states listed below.  
- [go to attribute list](#data_quality-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Detector  
The Detector class contains attributes describing the state of the instrument detector. These are values directly read from the detector and do not necessarily reflect the state of the image after onboard processing. For example, the entire image may be read into memory and then subframed in software, in which case the subframe attributes in this class reflect the entire image (as read from the detector), whereas those in the Subframe class represent the final subframe results.  
- [go to attribute list](#detector-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Device_Component_State  
The Device_Component_State class describes the state of one component of an imaging instrument or other imaging device. The meaning of "state" is device-specific.  
- [go to attribute list](#device_component_state-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Component_States  
The Device_Component_States class provides a container for the set of states of a component of an imaging instrument or other imaging device.  
- [go to attribute list](#device_component_states-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Device_Current  
The Device_Current class provides the current of some point on an imaging instrument or other imaging device.  
- [go to attribute list](#device_current-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Currents  
The Device_Currents class provides a container for the set of currents of an imaging instrument or other imaging device.  
- [go to attribute list](#device_currents-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Device_Motor_Count  
The Device_Motor_Count class describes the raw motor count of one actuator on an imaging instrument or other imaging device (such as a filter wheel, focus motor, or zoom motor). This information should typically be reported in a more specific and useable form in other classes, such as a filter number or wavelength in the Optical_Filter class or a focus distnace in the Focus class.  
- [go to attribute list](#device_motor_count-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Motor_Counts  
The Device_Motor_Counts class provides a container for the set of raw motor counts of actuators on an imaging instrument or other imaging device (such as a filter wheel, focus motor, or zoom motor).  
- [go to attribute list](#device_motor_counts-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Device_Parameters  
The Device_Parameters class identifies where a measurement was made. It may refer to an individual imaging instrument, imaging instrument device, or some defined point on the instrument or device. The class is intended to be extended (for example, by Device_Temperature) to add the associated measurement rather than being used directly.  
- [go to attribute list](#device_parameters-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Device_Temperature  
The Device_Temperature class provides a container for the temperature of some point on an imaging instrument or other imaging device.  
- [go to attribute list](#device_temperature-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Temperatures  
The Device_Temperatures class provides a container for the set of temperatures of an imaging instrument or other imaging device.  
- [go to attribute list](#device_temperatures-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Device_Voltage  
The Device_Voltage class provides the voltage of some point on an imaging instrument or other imaging device.  
- [go to attribute list](#device_voltage-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Voltages  
The Device_Voltage class provides a container for the set of voltages of an imaging instrument or other imaging device.  
- [go to attribute list](#device_voltages-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Downsampling  
 The Downsampling class describes whether or not downsampling occurred, the venue where it occurred (Software or Hardware), the method used to downsample, and the pixel averaging dimensions. A downsampled image is a smaller version of the image, resulting in reduced resolution of the same coverage area. The processing_algorithm attribute specifies the pixel resolution downsample method used. This varies by mission, but examples from MSL include: 'Mean' - Downsampling done in software by calculation of the mean., 'Conditional' - Use hardware binning if downsampling (by mean calculation) and subframe arguments are consistent.  
- [go to attribute list](#downsampling-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Exposure  
The Exposure class contains attributes identifying the image instrument exposure configuration and image exposure values. As a child of the Imaging class, these attribute values identify the actual exposure values when the image was taken. As a child of the Commanded_Parameters class, these attribute values are those that were commanded to the spacecraft at the time the image was taken.  
- [go to attribute list](#exposure-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### External_Reference  
The External_Reference class is used to reference a source outside the PDS registry system.  
- [go to attribute list](#external_reference-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Flat_Field_Correction  
 The Flat_Field_Correction class specifies how flat-field correction was performed on this image. This can be done either algorithmically, using a Radial_Flat_Field_Correction, or using a Flat_Field_File.  
- [go to attribute list](#flat_field_correction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Flat_Field_File  
The Flat_Field_File class specifies the image used for flat field correction. The image is divided by this flat field image in order to apply the flat field correction (which is the opposite of Radial_Flat_Field_Function).  
- [go to attribute list](#flat_field_file-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Focus  
The Focus class contains attributes that describe the focus or autofocus parameters for an observation. As a child of Commanded_Parameters, these indicate the focus settings used to command the instrument. Otherwise, they indicate the actual focus used by the observation.  
- [go to attribute list](#focus-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Focus_Stack  
The Focus_Stack class contains attributes that describe a set of images taken at different focus settings, which are often merged to create a best-focus image or combined to extract range information. Focus stacks are also sometimes called ZStacks.  
- [go to attribute list](#focus_stack-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Frame  
The Frame class contains attributes providing information specific to an image frame. A frame consists of a sequence of measurements made over a specified time interval, and may include measurements from different instrument modes. In the context of Frame, product_flag refers to the actual image.  
- [go to attribute list](#frame-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### High_Dynamic_Range  
Specifies parameters related to High Dynamic Range processing, which combines multiple exposures of different lengths into a single product with a greater dynamic range than any of the inputs.  
- [go to attribute list](#high_dynamic_range-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### High_Dynamic_Range_Exposure  
Specifies parameters for each individual exposure in an HDR image.  
- [go to attribute list](#high_dynamic_range_exposure-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Histogram  
Describes a Histogram product.  
- [go to attribute list](#histogram-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Hot_Pixel  
Specifies a data class that describes pixels whose responsivity on the sensor exceeds by some amount that of the average detector element.  
- [go to attribute list](#hot_pixel-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### ICER_Parameters  
 The ICER_Parameters class contains attributes describing onboard compression parameters specific to Joint Photographic Experts Group (JPEG) image compression. ICER is a wavelet-based image compression file format used by the NASA Mars Rovers. ICER has both lossy and lossless compression modes.  
- [go to attribute list](#icer_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### ISO  
The ISO Class contains the iso_number and iso_mode_id attributes. This class is added to support more commercial off-the-shelf (COTS) cameras or instruments which typically use this value to specify a setting for the instrument's sensitivty to light. If is often analogous to gain. ISO Sensitivity is a standard set by the International Organization for Standardization (ISO). A lower ISO value means less sensitivity to light, while a higher ISO means more sensitivity. Values defined here should generally conform to the ISO standard 12232:2019  
- [go to attribute list](#iso-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Illumination  
 The Illumination class provides attributes describing the illumination sources used to illuminate the imaging target.  
- [go to attribute list](#illumination-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Image_Compression_Segment  
 The Image_Compression_Segment class provides attributes describing each segment into which data was partitioned for error containment purposes as part of the compression process.  
- [go to attribute list](#image_compression_segment-attribute-list)  
- in [ICER_Parameters](#icer_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [JPEG_Parameters](#jpeg_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [JPEG_Progressive_Parameters](#jpeg_progressive_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [LOCO_Parameters](#loco_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [StarPixel_Flexible_Parameters](#starpixel_flexible_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [StarPixel_Lossless_Parameters](#starpixel_lossless_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
  
### Image_Filter  
The Image_Filter class specifies what kind of image filtering has been done to the image. Image filtering looks at image intensity rather the geometry of pixels (cf. Spatial_Filter).  
- [go to attribute list](#image_filter-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Image_Mask  
The Image_Mask specifies how pixels were masked (removed) from an image. Masks are typically used to suppress results in areas where they don't belong, for example masking off spacecraft hardware or removing pixels that did not meet some processing threshold.  
- [go to attribute list](#image_mask-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Image_Mask_File  
This class identifies a file used for image masking. The mask_type defines the type of file; if mask_type is missing then "image" is assumed.  
- [go to attribute list](#image_mask_file-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Imaging  
The Imaging class contains classes and attributes describing both the image product itself and the imaging instrument. Image product information can include exposure duration, filters, data correction, sampling, frame, sub-frames, and how the product was derived. For the imaging instrument, information can be provided describing the dynamic physical or operating characteristics of the imaging instrument.  
- [go to attribute list](#imaging-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Instrument_State  
The Instrument_State class contains classes providing the values of any dynamic physical or operating characteristics of the imaging instruments.  
- [go to attribute list](#instrument_state-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Internal_Reference  
The Internal_Reference class is used to cross-reference other products in PDS4-compliant registries of PDS and its recognized international partners.  
- [go to attribute list](#internal_reference-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### JPEG_Parameters  
 The JPEG_Parameters class contains attributes describing onboard compression parameters specific to Joint Photographic Experts Group (JPEG) image compression.  
- [go to attribute list](#jpeg_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### JPEG_Progressive_Parameters  
 The JPEG_Progressive_Parameters class contains attributes describing an interlaced progressive JPEG format, in which data is compressed in multiple passes of progressively higher detail. This is ideal for large images that will be displayed while downloading over a slow connection, allowing a reasonable preview after receiving only a portion of the data.  
- [go to attribute list](#jpeg_progressive_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### LED_Illumination_Source  
The LED_Illumination_Source class provides attributes describing an individual LED used to illuminate an imaging target.  
- [go to attribute list](#led_illumination_source-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### LOCO_Parameters  
 The LOCO_Parameters class contains attributes describing onboard compression parameters specific to Low Complexity Lossless Compression (LOCO) image compression, a lossless submode of ICER  
- [go to attribute list](#loco_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### List_Index_No_Units_Imaging  `*abstract*`  
Used when the list values have no units.  
- [go to attribute list](#list_index_no_units_imaging-attribute-list--abstract)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Local_Internal_Reference  
The Local Internal_Reference class is used to cross-reference other Description Objects in a PDS4 label.  
- [go to attribute list](#local_internal_reference-attribute-list)  
- in [Imaging](#imaging):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
- in [Optical_Filter](#optical_filter):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Tile](#tile):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Nonlinear_Pixel  
A data class describing pixels where electronic non-linear behavior may occur.  
- [go to attribute list](#nonlinear_pixel-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Onboard_Color_Matrix  
The Onboard_Color_Matrix class represents a 3x3 matrix that is used onboard to perform color correction. It is done after de-Bayering, as all three color bands are needed for each pixel. The first three elements are multiplied by the R,G,B (respectively) pixel values and summed to get the output Red pixel value. Similarly, the second three create the output Green, and the last three the output Blue. If the label is not present, no correction was performed.  
- [go to attribute list](#onboard_color_matrix-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Onboard_Compression  
The Onboard_Compression class contains attributes describing the compression performed onboard a spacecraft or instrument for data storage and transmission.  
- [go to attribute list](#onboard_compression-attribute-list)  
- in [Commanded_Parameters](#commanded_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [Imaging](#imaging):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [Reference_Pixel](#reference_pixel):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Thumbnail](#thumbnail):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Onboard_Responsivity  
The Onboard_Responsivity class specifies factors that have been applied to the R, G, and B cells (respectively) of the Bayer pattern, before de-Bayering (demosaicking) takes place. The intent of these is to approximately balance the filters so the de-Bayering process is not skewed, and EDR/ILT products look reasonable before full radiometric or color correction is done on the ground. If these factors are not present, no correction was performed.  
- [go to attribute list](#onboard_responsivity-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Optical_Filter  
The Optical_Filter class defines the filters used by the camera optics (not to be confused with image processing software filters). The filter may be identified by name, identifier, number, or some combination of these.  
- [go to attribute list](#optical_filter-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Optical_Properties  
The Optical_Properties class describes properties of the optics used in acquiring the image.  
- [go to attribute list](#optical_properties-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Pixel_Averaging_Dimensions  
The Pixel_Averaging_Dimensions class provides the height and width, in pixels, of the area over which pixels were averaged prior to image compression.  
- [go to attribute list](#pixel_averaging_dimensions-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Pointing_Correction  
The Pointing_Correction class contains attributes used to identify and describe the camera model transformations completed in order to update pointing information of an image or mosaic.  
- [go to attribute list](#pointing_correction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Pointing_Correction_File  
The Pointing_Correction_File class identifies a file containing pointing correction information.  
- [go to attribute list](#pointing_correction_file-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Pointing_Correction_Image  
The Pointing_Correction_Image class contains attributes used to identify and describe the camera model transformations completed in order to update pointing information of a single image, whether alone or part of a mosaic.  
- [go to attribute list](#pointing_correction_image-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Pointing_Model_Parameter  
The Pointing_Model_Parameter class specifies the name and value (numeric) parameters needed by the pointing model identified by the pointing_model_name attribute in the Pointing_Correction parent class. The meaning of any given parameter is defined by the pointing model.  
- [go to attribute list](#pointing_model_parameter-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Radial_Flat_Field_Function  
The Radial_Flat_Field_Function class pecifies parameters used to generate a synthetic flat field using a simple radial function of the form: r = (x-x_center)^2 + (y-y_center)^2 ; flat_field(x,y) = 1 + r0 + r1*r + r2*r^2 + r3*r^3 . Note that x is in the sample direction of the image, and y is in the line direction. The image is multiplied by this function in order to perform a flat field correction (which is the opposite of Flat_Field_File).  
- [go to attribute list](#radial_flat_field_function-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Radiometric_Correction  
 The Radiometric_Correction class is a container for the type and details of the radiometric calibration performed on the product.  
- [go to attribute list](#radiometric_correction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Reference_Pixel  
Describes a Reference Pixel product, which is a set of dark, non-imaging pixels used to monitor electronics. product_flag.  
- [go to attribute list](#reference_pixel-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Row_Sum  
Describes a Row Summation product, which is a single column containing the sum of all pixels in each row of the image.  
- [go to attribute list](#row_sum-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Sampling  
 The Sampling class contains attributes and classes related to the sampling, scaling, companding, and compression or reduction in resolution of data.  
- [go to attribute list](#sampling-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Saturated_Pixel  
A data class that describes pixels within the image have reached or exceeded the maximum pixel value.  
- [go to attribute list](#saturated_pixel-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Shutter  
Shutter is a class to hold information for shutter type of camera. Currently only "Global" or "Rolling" are allowed. Global normally exposes all pixels at the same time, so the image captures a consistent view of moving objects. Rolling scans across the scene, meaning each pixel is exposed at a slightly different time, which can introduce distortions for rapidly moving objects. This is generally a property of the camera itself and does not vary from frame to frame.  
- [go to attribute list](#shutter-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Shutter_Subtraction  
 The Shutter_Subtraction class specifies attributes describing the removal from the image of the shutter, or fixed-pattern.  
- [go to attribute list](#shutter_subtraction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Spatial_Filter  
The Spatial_Filter class specifies what kind of spatial filtering has been done on the image. Spatial filtering looks at the geometry of pixels (e.g. XYZ or range values) rather than their intensity (cf. Image_Filter).  
- [go to attribute list](#spatial_filter-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Special_Point  
Defines a special point on the image detector, such as the location in pixel space that a co-boresighted instrument measures.  
- [go to attribute list](#special_point-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### StarPixel_Flexible_Parameters  
 The StarPixel_Flexible_Parameters class contains attributes describing onboard compression parameters specific to StarPixel Flexible image compression. StarPixel Flexible is developed based on StarPixel Lossless and used by the JAXA's spacecraft, Hayabusa2. StarPixel Flexible is a lossy compression algorithm.  
- [go to attribute list](#starpixel_flexible_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### StarPixel_Lossless_Parameters  
 The StarPixel_Lossless_Parameters class contains attributes describing onboard compression parameters specific to StarPixel Lossless image compression. StarPixel Lossless is developed based on FELICS and used by the JAXA's spacecrafts, Akatsuki and Hayabusa2. StarPixel Lossless is a lossless compression algorithm and also known as HIREW.  
- [go to attribute list](#starpixel_lossless_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Subframe  
 The Subframe class describes the position and other optional characteristics of an image subframe, relative to the original image.  
- [go to attribute list](#subframe-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Thumbnail  
Describes a Thumbnail product, which is a greatly reduced resolution version of the image.  
- [go to attribute list](#thumbnail-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Tile  
Contains parameters that describe how an image was or will be broken into tiles, before reassembly into a whole. This is generally intended for cameras that break up an exposure into tiles for transmission, but can also be used to describe tiling done by a ground system (e.g. for display purposes) if needed. Tiles need not be regular nor do they need to cover the entire area, and irregular tiles may overlap. Note that the image in which this class appears is expected to contain all the tiles (i.e. not just a single tile).  
- [go to attribute list](#tile-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Tiling  
Contains parameters that describe how an image was or will be broken into tiles, before reassembly into a whole. This is generally intended for cameras that break up an exposure into tiles for transmission, but can also be used to describe tiling done by a ground system (e.g. for display purposes) if needed. Tiles need not be regular nor do they need to cover the entire area, and irregular tiles may overlap. Note that the image in which this class appears is expected to contain all the tiles (i.e. not just a single tile).  
- [go to attribute list](#tiling-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Video  
The Video class contains attributes related to video observations, defined as a regular time series of frames. The class can be used to describe a single frame within the video, or the video as a whole.  
- [go to attribute list](#video-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### White_Balance  
The White_Balance class indicates what processing was used for white balance either onboard or on the ground. This class is added to support more commercial off-the-shelf (COTS) cameras. The white balance for a camera tries to capture the image using the correct colors in relation to the light source. For COTs cameras, the white balance is usually automatically adjusted depending on the light source.  
- [go to attribute list](#white_balance-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
## Attributes (in alphabetical order)  
  
### *above_aft_flag*  
A boolean value that denotes the camera mechanism was above allowable flight temperature at time of acquisition.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *active_flag*  
The active_flag attribute indicates whether or not the data processing described by the parent class is active. In general, the presence of the parent class implies it is active and thus active_flag is optional. The primary purpose for active_flag is to either explicitly indicate a correction is not active (for example, if it normally is but was explicitly turned off), or to be able to provide parameters for historical reasons that may no longer be relevant to a current correction.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *analog_offset*  
The analog_offset attribute identifies the analog value that is subtracted from the signal prior to the analog/digital conversion. This is a unitless integer and should generally be avoided in favor of analog_offset_count, if the value is a raw DN value, or one of the other analog_offset attributes if it has a physical unit  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *analog_offset_count*  
Raw counts for analog offset.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *analog_offset_percent*  
Multiplier applied to pixel depth to get black level (also known as analog_offset). For example: 4% = .04 * 256 = 10.24 for 8-bit images or 4% * 4096 = 163.84 for 12-bit images.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *analog_offset_voltage*  
Specifies the analog voltage value that is subtracted from the signal prior to the analog/digital conversion.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *array_band_number*  
The array_band_number is the image plane (band) in the array that corresponds to the optical filter with which the image was acquired.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *atmospheric_opacity*  
The atmospheric opacity (tau) value used in radiometric correction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *atmospheric_opacity_reference*  
The atmospheric opacity (tau) target value to which the image was corrected.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_expose_target_dn*  
Target DN for an autoexpose algorithm. Specific definition is algorithm-dependent, but often means the desired average DN after autoexposure completes.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_alpha*  
auto_exposure_alpha is a weighting parameter that decides whether to prefer exposure changes more or gain changes. Values closer to 1 mean exposure changes are preferred more. For example, this will be used by the CADRE rovers which have a different autoexposure algorithm called "ModalAI MSV 2022".  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_data_cut*  
The auto_exposure_data_cut attribute specifies the DN value which a specified fraction of pixels is permitted to exceed. The fraction is specified using the auto_exposure_data_fraction attribute.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_lower_limit*  
Specifies the maximum number of pixels that are allowed to be below the lower threshold defined by auto_exposure_lower_limit.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_lower_threshold*  
Specifies the lower threshold DN value for which a specified number of pixels is permitted to exceed. The auto_exposure_lower_limit defines the number of pixels allowed to exceed this threshold.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_max_delta*  
The maximum exposure change that is allowed across image frames. Limiting the change makes it more friendly to feature tracking algorithms, in that successive scenes do not vary greatly in brightness. For example, this will be used by the CADRE rovers which have a different autoexposure algorithm called "ModalAI MSV 2022".  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_percent*  
The auto_exposure_percent attribute specifies the auto-exposure early-termination percent. If the desired DN (auto_exposure_data_cut) is within this percentage of the measured DN (the DN at which the percentage of pixels above that DN equals or exceeds the auto_exposure_pixel_fraction), then the auto exposure algorithm is terminated and the calculated time is accepted.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_pixel_fraction*  
The auto_exposure_pixel_fraction attribute specifies the percentage of pixels whose DN values may exceed the auto_expsoure_data_cut.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_roi_first_line*  
Specifies the (1-based) starting line for the autoexposure region of interest.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_roi_first_sample*  
Specifies the (1-based) starting sample for the autoexposure region of interest.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_roi_lines*  
Specifies the number of lines in the autoexposure region of interest.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_roi_samples*  
Specifies the number of samples in the autoexposure region of interest.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_target_msv*  
The algorithm attempts to make the Mean Sample Value (MSV) of the image match for this value. For example, this will be used by the CADRE rovers as the setpoint for the algorithm called "ModalAI MSV 2022".  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_upper_limit*  
Specifies the maximum number of pixels that are allowed to be above the upper threshold defined by auto_exposure_upper_limit.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *auto_exposure_upper_threshold*  
Specifies the upper threshold DN value for which a specified number of pixels is permitted to exceed. The auto_exposure_upper_limit defines the number of pixels allowed to exceed this threshold.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *autofocus_step_count*  
 The autofocus_step_count attribute specifies the number of steps (images) to be taken by an autofocus algorithm.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *autofocus_step_size*  
The autofocus_step_size attribute specifies the size in motor counts of each (or the initial) step taken by the focus adjustment mechanism in an autofocus algorithm.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *bad_pixel_replacement_flag*  
If true, specifies whether or not bad pixel replacement processing was requested or completed. See bad_pixel_replacement_table_id.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *bad_pixel_replacement_table_id*  
Specifies the table used to replace bad pixels. A bad pixel table typically lists the location of each bad pixel on a detector. The specific table used is mission-specific.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *bandwidth*  
The bandwidth attribute provides a measure of the spectral width of a filter. For a root-mean-square detector this is the effective bandwidth of the filter, i.e. the full width of an ideal square filter having a flat response over the bandwidth and zero response elsewhere. Another common method for measuring bandwidth is Full Width at Half Maximum, which is the width of a "bump" on a curve or function. It is given by the distance between points on the curve at which the function reaches half of its maximum value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *below_aft_flag*  
A boolean value that denotes the camera mechanism was above allowable flight temperature at time of acquisition.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *best_focus_distance*  
The best_focus_distance attribute specifies the estimated distance to best focus.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *brightness_offset*  
The brightness_offset attribute defines the additive factor used for a linear brightness correction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *brightness_scale*  
The brightness_scale attribute defines the multiplicative factor used for a linear brightness correction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *center_filter_wavelength*  
The center_filter_wavelength attribute provides the wavelength of the center of the passband, or the peak transmissivity, for an instrument filter.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *color_component*  
For single-band images, this defines which component of the color space is represented by this band. This keyword is not needed for 3-band images, as all bands are represented.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *color_dn_scaling_factor*  
The color_dn_scaling_factor attribute specifies the actual value used to scale the color values. This value is determined using the color_dn_scaling_method.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *color_dn_scaling_method*  
The color_dn_scaling_method attribute defines how the color values are scaled. EXPOSURE_NORMALIZED_COLOR means that the color values have been normalized based on exposure time, so neighboring images in a mosaic will have the same color values. DN_COLOR means that the color values are based on the raw DNs, so images take full advantage of the available dynamic range but may not match with neighbors in a mosaic.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *color_filter_array_state*  
Specifies whether the image still has a CFA pattern ("Encoded"), the CFA pattern has been removed ("Decoded") or it never had a pattern ("No CFA").  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Decoded  
    - Description: Indicates the image has been processed such that it no longer contains the CFA pattern. This generally means the image is color, but it could also mean that processing has been applied to remove the effects of the CFA pattern and still be a single band, or that the result is a multispectral image. The algorithm used to decode the pattern is indicated by the processing_algorithm attribute in the Color_Filter_Array class.  
  - Encoded  
    - Description: Indicates the CFA pattern is still present in the image. The image should be a single band, with each pixel containing the appropriate color value as determined by the color_filter_array_type. An encoded image is not directly viewable as color; it must be decoded first.  
  - No CFA  
    - Description: Indicates the image is not and has never been CFA encoded. In this case, Color_Filter_Array would simply not be present in the label. This value is present in case it needs to be explicitly stated that there is no CFA.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *color_filter_array_type*  
Defines the type of Color Filter Array (CFA) used to encode multiple colors in a single exposure. The most common example of this is the Bayer pattern. This is optional if there is no CFA. Additional attributes, specific to each CFA type, define whether or not the CFA pattern has been removed, and if so, how (e.g. bayer_algorithm).  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Bayer RGGB  
    - Description: The Bayer CFA pattern contains one red, one blue, and two green pixels in each 2x2 square of pixels. The RGGB type indicates the phasing of the colors, in the order upper left, upper right, lower left, and lower right. RGGB is the most common phasing but others are possible.  
  - Bayer RGYB  
    - Description: The Bayer CFA pattern contains one red, one green, one yellow, and one blue pixel in each 2x2 square of pixels. The RGYB type indicates the phasing of the colors, in the order upper left, upper right, lower left, and lower right.  
  - None  
    - Description: No color filter array  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *color_space*  
Defines the color space in which this product is expressed. Some color spaces (e.g. XYZ or xyY) are independent of illuminant, while for others (e.g. sRGB or pRGB) the illuminant matters. It is expected that the defined color spaces will increase over time.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *color_subsampling_mode*  
 The color_subsampling_mode attribute specifies the JPEG color subsampling mode used during compression. Valid values: '4:2:2' - 4:2:2 chroma subsampling, which is the typical case, '4:4:4' - 4:4:4 chroma sampling, which indicates no subsampling, 'Grayscale' - indicates a grayscale image  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - 4:2:2  
    - Description: indicates 4:2:2 chroma subsampling. The typical case. The two chroma components are sampled at half the sample rate of luma: the horizontal chroma resolution is halved. This reduces the bandwidth of an uncompressed video signal by one-third with little to no visual difference.  
  - 4:4:4  
    - Description: Indicates 4:4:4 chroma sampling. Each of the three Y'CbCr components have the same sample rate, thus there is no chroma subsampling  
  - Grayscale  
    - Description: indicates a grayscale image  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *comment*  
The comment attribute is a character string expressing one or more remarks or thoughts relevant to the object.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *companding_state*  
The companding_state attribute specifies whether the data is or has had its bit depth reduced, for example conversion from 12 to 8 bits via a lookup table or bit scaling. Valid values: None - values have not been companded. Companded - values are currently companded. Expanded - values have been companded but are now expanded back to original size.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Companded  
    - Description: values are currently companded  
  - Expanded  
    - Description: values have been companded but are now expanded back to original size  
  - None  
    - Description: values have not been companded  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *crosstrack_summing*  
The crosstrack_summing attribute provides the number of detector pixel values in the crosstrack direction that have been averaged to produce the final output pixel.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *current_value*  
The current_value attribute provides provides the current, in the specified units, of an imaging instrument or some part of the imaging instrument.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *data_received*  
This field defines if all parts of the data or image is received without detected checksum or sequence errors. Example use case from MRO CTX is either "OK" if all fragments of the image were received or "ERROR" if not.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *decomposition_stages*  
 The decomposition_stages attribute identifies the number of stages of decomposition.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *deferred_flag*  
 The deferred_flag attribute specifies whether compression was done at the time of image acquisition, or was deferred until later (typically at downlink time).  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *delta_focus_count*  
Defines the amount of change in focus for each image in the z-stack. The units should be the same as focus_position_count, which is often motor counts.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *description*  
The description attribute provides a statement, picture in words, or account that describes or is otherwise relevant to the object.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *detector_to_image_flip*  
The detector_to_image_flip attribute indicates whether and how the image was flipped (mirror image) along its optical path through an instrument, from detector to final image orientation. "Horizontal" means a left-to-right flip, while "Vertical" means a top-to-bottom-flip. Note that if both this attribute and detector_to_image_rotation exist, the flip is assumed to have happened before the rotation.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Horizontal  
    - Description: Horizontal means a left-to-right flip  
  - None  
    - Description: None, meaning no flip applied, is optionally added for completeness. Otherwise this attribute can simply not be included.  
  - Vertical  
    - Description: Vertical means a top-to-bottom-flip  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *detector_to_image_rotation*  
 The detector_to_image_rotation attribute specifies the clockwise rotation, in degrees, that was applied to an image along its optical path through an instrument, from detector to final image orientation. Note that if both this attribute and detector_to_image_flip exist, the flip is assumed to have happened before the rotation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 360.0  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *device_id*  
The device_id attribute supplies the identifier of an imaging instrument, an imaging instrument device, or some point on the instrument or device.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *device_name*  
The device_name attribute supplies the formal name for an imaging instrument, an imaging instrument device, or some point on the instrument or device.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *device_state*  
The device_state attribute indicates the state of a sensor or other device associated with the imaging instrument. These states are interpreted in an instrument-specific way.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *download_priority*  
The download_priority attribute specifies which data to downlink/transmit, based on order of importance. The ranking and meaning of specific values will vary depending on the mission, and should be defined in the mission software interface specification (SIS).  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *downtrack_summing*  
The downtrack_summing attribute provides the number of detector pixel values in the downtrack direction that have been averaged to produce the final output pixel.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *dq_band*  
Specifies the sequence number in the data array to which the data quality indicators apply.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *dq_bayer_cell*  
Specifies the Bayer cell to which the data quality indicators apply. bayer_cell can be used even if the image has been debayered, in which case it refers to the original debayered image. Note that "green_1" and "green_2" can be used to refer to specific green Bayer cells, or "green" refers to both greens together.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum value: 1  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *early_image_return*  
Indicates is there was a deferral of on-board post-processing of an image. For MSL, returns the image early to an onboard client. Early processing includes rotation, bad pixels, flat field, early scaling, and camera model production.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *early_scaling*  
If true, indicates that the companding was or should be done "early" in the onboard processing chain, for instruments where there is an option. For MSL, early processing is where the image is prepared for use by any client, including those on board, such as rotation, bad pixels, flat field, early scaling, and camera model production. Contrast that with late processing, which includes compression and telemetry generation, and processing for thumbnails, subframes, histograms, and row/column sums.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *effective_wavelength*  
Defines the weighted average of the system response and solar spectrum.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *encoded_display_gamma*  
Defines the gamma value encoded in this image. Gamma correction is used to nonlinearly compress the intensities in an image, and most display systems assume that images are encoded with an sRGB gamma. Note that this is a string value because the most common gamma correction ("sRGB") is not precisely expressible as a gamma exponent. A numeric value indicates a gamma exponent.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *erase_count*  
The erase_count specifies the number of times a detector has been or will be flushed of data in raw counts, dependent on the parent class for the attribute.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *error_pixel_count*  
 The error_pixel_count attribute specifies the number of pixels that are outside a valid DN range, after all decompression and post decompression processing has been completed.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_coadd_count*  
Specifies the total number of exposures summed (co-added) together to obtain the final image. Co-adding increases the signal-to-noise ratio.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Minimum Length: 0  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_count*  
The exposure count attribute provides the number of exposures taken during a certain interval, such as the duration of one command. For example, this may include the number of exposures needed by an autoexpose algorithm.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_duration*  
The exposure_duration attribute provides the amount of time the instrument sensor was gathering light from the scene, such as between opening and closing of a shutter, or between flushing and readout of a CCD.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_duration_count*  
The exposure_duration_count attribute specifies the value, in raw counts, for the amount of time the instrument sensor was gathering light from the scene, such as between opening and closing of a shutter, or between flushing and readout of a CCD. This is the raw count either commanded or taken directly from telemetry as reported by the spacecraft. This attribute is the same as the exposure_duration but in DN counts instead of time, and the translation of exposure_duration_count to exposure_duration will differ by mission.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_duration_threshold_count*  
The exposure_duration_threshold specifies the exposure time threshold in raw counts, when shutter_subtraction_mode = 'Conditional'.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_readout_count*  
Specifies the number of times an exposure, or part of an exposure, has been read from the camera. Multiple readouts could be due to tiling of the image, among other reasons.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Minimum Length: 0  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_scale_factor*  
Specifies a multiplier to the base exposure time. The base exposure time is either user-commanded or is read from the onboard exposure time table. The resulting number is used by the cameras as the actual commanded exposure time. This scale factor is commonly used during multi-spectral imaging, when the base exposure time is known for one filter and exposure_scale_factor is used to scale the exposure time to levels appropriate for the other filters.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_table*  
Identifies the exposure table to be used, or that was used. The exposure table provides the seed exposure value to use for each camera for the autoexposure algorithm.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_table_update_flag*  
If true, specifies whether or not to update the autoexposure table based on the results of this exposure.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_time_delta*  
Specifies the change in exposure time for this exposure compared to the previous. Should be 0 for the first item in the list.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_type*  
The exposure_type attribute indicates the exposure setting on a camera. Valid values: 'Manual' - manual exposure setting, 'Auto' - autoexposure is applied by the camera, 'Test' - test exposure setting telling the camera to return a fixed-pattern test image.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Auto  
    - Description: Autoexposure is applied by the camera.  
  - Auto Last  
    - Description: Autoexposure using prior image as a seed.  
  - Manual  
    - Description: Manual exposure setting.  
  - Manual Last  
    - Description: Use same exposure as the prior image.  
  - None  
    - Description: No exposure requested.  
  - Test  
    - Description: Test exposure setting telling the camera to return a fixed-pattern test image.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *f_number*  
Defines the f/number for the optics used in acquiring the image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *filter_id*  
 The filter_id attribute provides a short string identifier for an instrument filter through which an image or measurement was acquired or which is associated with a given instrument mode.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 16  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *filter_name*  
The filter_name attribute provides the name, described in the mission documentation, of the optical filter through which an image or measurement was acquired.  
- PDS4 data type: UTF8_Short_String_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *filter_number*  
The filter_number attribute provides the numeric identifier of an instrument filter through which an image or measurement was acquired or which is associated with a given instrument mode.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *filter_position_count*  
The filter position count is the position in motor counts of the filter wheel motor.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *filter_window_line*  
The size in pixels of the window used for filtering in the line dimension. If the window varies across the image, this could contain the average window or initial window, as needed by the specific algorithm.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *filter_window_sample*  
The size in pixels of the window used for filtering in the sample dimension. If the window varies across the image, this could contain the average window or initial window, as needed by the specific algorithm.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *first_line*  
The first_line attribute indicates the line within a source image that corresponds to the first line in a sub-image.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- in [Detector](#detector):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Image_Compression_Segment](#image_compression_segment):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Subframe](#subframe):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *first_sample*  
 The first_sample attribute indicates the sample within a source image that corresponds to the first sample in a sub-image.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- in [Image_Compression_Segment](#image_compression_segment):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Detector](#detector):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Subframe](#subframe):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *focal_length*  
Defines the focal length of the optics used in acquiring the image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_distance*  
The nominal focus distance for the instrument (e.g. in meters or mm). This is often the commanded value, or autofocus seed value, but can also be used to indicate a nominal distance where the connotation of "best" is not appropriate (see best_focus_distance).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_initialization_flag*  
Specifies whether the instrument focus mechanism should be (or was) initialized before use.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_merge_blending_flag*  
The focus_merge_blending_flag attribute indicates whether intra-stack image blending has been performed during a focus merge operation. A value of 'false' means images were merged without blending.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_merge_registration_flag*  
The focus_merge_registration_flag attribute indicates whether intra-stack image registration has been performed during a focus merge operation. A value of 'true' indicates that intra-stack image registration has been performed during the focus merge operation, while 'false' indicates that images have been merged without translation.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_mode*  
The focus_mode attribute specifies the type of focus command, for example: Autofocus, Manual, ZStack, or Relative (focus adjustment based on a previous autofocus).  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_position*  
The focus_position attribute defines, in a camera-specific way, the focus metric that should be used for geometric processing of the data (e.g. for creating camera models). This will often be the focus motor count.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_position_count*  
The focus_position_count attribute specifies a commanded focus, or the initial focus position used by the autofocus algorithm.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *focus_stack_flag*  
 The focus_stack_flag attribute indicates whether or not focus stack image products were created during the autofocus imaging step.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_count*  
 The frame_count attribute indicates the total number of image frames acquired, such as for a video or focus stack observation.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_id*  
The frame_id attribute specifies an identification for a particular instrument measurement frame. A frame consists of a sequence of measurements made over a specified time interval, and may include measurements from different instrument modes. These sequences repeat from cycle to cycle and sometimes within a cycle.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_index*  
When in a Video class, the frame_index attribute specifies the sequence number of this frame in the context of the entire video, i.e. the first frame of the video would be index 1, up to frame_count. When in a Focus_Stack class, the frame_index attribute specifies the index of the first frame used to make up the focus stack. M2020 requested to allow negative values which has been seen as returned values during the mission.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_interval*  
The frame_interval attribute defines the time between the start of successive frames in a video product.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_rate*  
 The frame_rate attribute specifies the calculated frame rate for video products.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_readout_time*  
Specifies the time it takes for readout of the entire camera frame. This is the time from readout of the first pixel to the readout of the last pixel and does not include exposure time or other delays.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_source_id*  
frame_source_id is a mission-specific ID string identifying the source of the video. For example, for the CADRE rover's SACA instrument, it would be a camera ID.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_type_name*  
 The frame_type_name attribute specifies whether the image was commanded as part of a stereo pair or as a single left or right monoscopic image. If frame_type = 'Stereo', a left and a right image should be present.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Mono  
    - Description:  image was commanded as a single left or right monoscopic image  
  - Stereo  
    - Description:  image was commanded as part of a stereo pair  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *full_well_limit_flag*  
A boolean value that denotes we have reached/exceeded the full well value of the CCD detector.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gain_count*  
Raw counts for gain.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gain_db*  
Gain is the amount of amplification that is applied to a pixel by the A/D converter. For example, an increase in gain can result in a brighter image but also an increase in noise.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gain_mode_id*  
The gain_mode_id attribute identifies the gain state of an instrument. Gain is a constant value which is multiplied with an instrument's output signal to increase or decrease the level of that output. These modes may vary by mission so the permissible values should be set by the mission dictionaries.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gain_number*  
The gain_number attribute specifies the gain value used in the analog to digital conversion. The gain value is a multiplicative factor used in the analog to digital conversion.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gop_frame_count*  
The gop_frame_count attribute indicates, for video products compressed into a group of images (Group Of Pictures or GOP), the number of images in a GOP. This is not necessarily the total number of frames in the observation (see frame_count), as the observation may consist of a number of GOPs.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gop_frame_index*  
Videos can be broken into Groups of Pictures (GOP)s, which group a number of frames together. The gop_frame_index attribute specifies the frame index within a Group Of Pictures (GOP) starting at 1. This is distinct from frame_index, which is the index into the video as a whole.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gop_start_index*  
Videos can be broken into Groups of Pictures (GOP)s, which group a number of frames together. The gop_start_index attribute specifies the index of the first frame of the GOP (starting at 1). Thus, frame_index = gop_start_index + gop_frame_index - 1.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *hdr_acquisition_mode*  
Specifies how the HDR frames were acquired.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Multiframe  
    - Description: HDR is processed using several separately-acquired images.  
  - None  
    - Description: No HDR processing.  
  - Piecewise  
    - Description: HDR is processed onboard the camera.  
  - Single  
    - Description: Single exposure.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *hdr_clipping_threshold*  
Specifies the threshold for pixel clipping.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *hdr_frame_count*  
Specifies the number of frames that go into the HDR product.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *height_pixels*  
The height_pixels attribute provides the vertical dimension, in pixels.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *horizon_mask_elevation*  
Specifies the elevation above which the image is masked off.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90.0  
- Maximum value: 90.0  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *icer_quality*  
For ICER, the quality is the "minloss" parameter, which specifies the minimum number of bit planes that will not be encoded in each subband. Note that ICER may stop due a byte quota before minloss is achieved, so the actual quality may be less than specified. Unlike JPEG, a lower number means higher quality.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *id*  
The id attribute supplies a short name (identifier) for the associated value in a group of related values.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *illuminant*  
Defines the illuminant that was used in order to process this image. The valid values are open-ended but examples of valid values include: None, D65, 3000K, 5000K.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *illumination_mode*  
illumination_mode describes what mode the illumination device is in. It could be used to indicate a common name for a particular configuration of activated lights, where there are many such devices. Current examples used include: Red, Green, Blue, White, UV, SLI-A Dense, SLI-B Sparse, Other, Off  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *illumination_state*  
The illumination_state attribute provides if the LED was On or Off.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Off  
    - Description: Illumination state (LED) is Off.  
  - On  
    - Description: Illumination state (LED) is On.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *illumination_wavelength*  
The illumination_wavelength attribute provides the wavelength of an LED that was used to illuminate this image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *image_corrupt_flag*  
Indicates whether or not this image was corrupted after it was acquired (i.e. it was corrupted somewhere downstream not part of acquisition). Valid values are "true", "false", "1" (one, as true), and "0" (zero, as false).  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *inband_fsun*  
This is the average solar flux at the top of the planetary atmosphere (or surface if there is no atmosphere) weighted by the system spectral response of the camera for the image in question. "Inband" means it is limited to the part of the spectrum that is in the passband of the camera, and "fsun" is mathematically written as F subscript sun. The value is in units of spectral radiance, and is calculated by dividing the weighted in-band integrated radiance of the sun by the bandpass of the camera (taking into account filter, zoom, and any other relevant settings).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *input_dn_max*  
The input_dn_max attribute provides the value of the maximum DN in the input image that is assigned a specific DN in the output image during companding.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *input_dn_min*  
The input_dn_min attribute provides the value of the minimum DN in the input image that is assigned a specific DN in the output image during companding.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *instrument_idle_timeout*  
Specifies the amount of time in seconds the instrument may be idle before powering off the instrument.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *interframe_delay*  
The interframe_delay attribute provides the time between the end of one frame and the beginning of the next frame in a video product.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *iof_conversion_coefficient*  
The iof_conversion_coefficient is a direct conversion factor from units of radiance to units of reflectance, calculated by plotting the observed reflected radiance of a calibration target versus modeled reflectance values.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *iof_conversion_coefficient_std*  
1-sigma standard deviation for the radiance factor (IOF) conversion coefficient.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *iof_conversion_correction*  
The iof_conversion_correction attribute is the correction factor applied to I/F. Can be used to account for differences in time of day between the calibration target and image acquisitions. For Mars2020 Mastcam-Z, this factor accounts for the differences in time of day between calibration target and image acquisitions and is only used when the factor is between 0.9 and 1.1.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *iso_mode_id*  
The iso_mode_id attribute is a mission specific definition of how the ISO value is actually used. For example, this could be set as "ISO 12232:2019" if the iso_number attribute follows the ISO standard 12232:2019, otherwise how it used should be defined here.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *iso_number*  
Specifies the ISO level set for the camera. ISO Sensitivity is a standard set by the International Organization for Standardization (ISO) that represents sensitivity to light as a numerical value as it pertains to either film or a digital sensor. A lower ISO value means less sensitivity to light, while a higher ISO means more sensitivity. The most common ISO values are 100, 200, 400, 800, 1600, and 3000. The lowest ISO setting or base ISO is typically 100, although some cameras go as low as 50 or even 25. Some older cameras will start at ISO 200. This should generally conform to ISO 12232:2019  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *jpeg_parameter*  
The jpeg_parameter attribute is a JPEG specific variable which specifies on-board compression determination by image quality or by compression factor, based on a selected on-board compression mode.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *jpeg_quality*  
The jpeg_quality attribute is a JPEG specific variable which identifies the resultant or targeted image quality index for on-board data compression.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 100  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *line_fov*  
The line_fov attribute specifies the angular measure of the field of view of an imaged scene, as measured in the image line direction (generally vertical).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 360.0  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *line_readout_time*  
Specifies the time between readout of the same pixel on adjacent lines. It it the time from the start of one pixel to the start of the same pixel on the following line.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *lines*  
The lines attribute indicates the total number of data instances along the vertical axis of an image or sub-image.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- in [Detector](#detector):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Image_Compression_Segment](#image_compression_segment):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Subframe](#subframe):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *mask_transparent_value*  
Specifies the pixel value in the mask that will represent transparent (or NoData/null) for the characterized image. This is normally defined as 0 in the mask layer. Once defined, any other value in the mask represents opaque or translucent (in other words, valid) in the characterized image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *mask_type*  
This identifies the type of mask file. Two enumerations are given, but these can be expanded if needed.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - description  
    - Description: A mask_type listed as "description" indicates that the file, e.g., a text or xml based file, describes the mask in some other way depending on the processing_algorithm.  
  - image  
    - Description: Most masks are of "image" type, this means it is an image of the same size as the current image containing mask information at each pixel.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *max_auto_exposure_iteration_count*  
The max_auto_exposure_iteration_count attribute specifies the maximum number of exposure iterations the instrument will perform in order to obtain the requested exposure.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *max_filter_window_line*  
The maximum size in pixels of the window used for filtering in the line dimension. If the window is constant across the image, filter_window_line should be used instead.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *max_filter_window_sample*  
The maximum size in pixels of the window used for filtering in the sample dimension. If the window is constant across the image, filter_window_sample should be used instead.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_focus_distance*  
The maximum_focus_distance attribute specifies the estimated distance to the farthest pixel with less than 1 pixel of gaussian blur.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *min_filter_window_line*  
The minimum size in pixels of the window used for filtering in the line dimension. If the window is constant across the image, filter_window_line should be used instead.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *min_filter_window_sample*  
The minimum size in pixels of the window used for filtering in the sample dimension. If the window is constant across the image, filter_window_sample should be used instead.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_focus_distance*  
The minimum_focus_distance attribute specifies the estimated distance to the nearest pixel with less than 1 pixel of gaussian blur.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *missing_pixel_count*  
 The missing_pixel_count attribute identifies the total number of missing pixels defined by the image or image segment.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *missing_temperature_flag*  
A boolean value that denotes temperature data was missing at time of image acquisition.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *motor_count*  
The motor_count attribute specifies the raw motor counts for the specified device, which indicates the position of the associated mechanism in a device-specific way.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *name*  
The name attribute provides a word or combination of words by which the object is known.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Illumination](#illumination):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Subframe](#subframe):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [LED_Illumination_Source](#led_illumination_source):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Correction_Parameter](#correction_parameter):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [List_Index_No_Units_Imaging](#list_index_no_units_imaging--abstract)  `*abstract*`:  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Special_Point](#special_point):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Brightness_Correction_File](#brightness_correction_file):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Companding_File](#companding_file):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Companding_Table](#companding_table):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Data_Processing_File](#data_processing_file):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Flat_Field_File](#flat_field_file):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Pointing_Correction_File](#pointing_correction_file):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Image_Mask_File](#image_mask_file):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Pointing_Model_Parameter](#pointing_model_parameter):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
  
### *no_signal_count*  
Integer number of pixels that received no signal above bias.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *num_line_tiles*  
Defines the number of tiles in the line direction for a regular tile. Not used for irregular tiles.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *num_sample_tiles*  
Defines the number of tiles in the sample direction for a regular tile. Not used for irregular tiles.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *observation_number*  
Identifies which observation of many this data product pertains to.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *onboard_B_b*  
Specifies the factor that has been multiplied by the B pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied R and G pixel values to produce the output Blue value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_B_g*  
Specifies the factor that has been multiplied by the G pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied R and B pixel values to produce the output Blue value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_B_r*  
Specifies the factor that has been multiplied by the R pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied G and B pixel values to produce the output Blue value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_G_b*  
Specifies the factor that has been multiplied by the B pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied R and G pixel values to produce the output Green value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_G_g*  
Specifies the factor that has been multiplied by the G pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied R and B pixel values to produce the output Green value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_G_r*  
Specifies the factor that has been multiplied by the R pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied G and B pixel values to produce the output Green value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_R_b*  
Specifies the factor that has been multiplied by the B pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied R and G pixel values to produce the output Red value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_R_g*  
Specifies the factor that has been multiplied by the G pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied R and B pixel values to produce the output Red value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_R_r*  
Specifies the factor that has been multiplied by the R pixel value after de-Bayering (demosaicking) takes place. This value is summed with the multiplied G and B pixel values to produce the output Red value.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *onboard_compression_class*  
The onboard_compression_class attribute identifies the type of on-board compression used for data storage and transmission. Note that the onboard_compression_type identifies the specific compression algorithm used (for example, ICER), whereas the onboard_compression_class gives a simple indicator of the type of compression mode. Valid values: 'Lossless', 'Lossy', 'Uncompressed'.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Lossless  
    - Description: Lossless compression means that after compression and decompression, the data is the same (bit-for-bit) as the original.  
  - Lossy  
    - Description: Lossy compression means that the data after decompression differs in some way from the data before compression.  
  - Uncompressed  
    - Description: Uncompressed data is also lossless, but use of the "Uncompressed" value indicates that data was not compressed.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *onboard_compression_mode*  
The onboard_compression_mode attribute identifies the method used for on-board compression, performed for the purpose of data storage and transmission. The value for this attributes represents the raw integer value for compression, which is then translated to the full name captured by the onboard_compression_type attribute.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *onboard_compression_quality*  
 The onboard_compression_quality attribute is an indication of compression quality, in the range of 0.0 to 1.0. Losslessly compressed or uncompressed data have a value of 1.0. Other values are assigned in a manner specific to the compression mode, but with the property that a higher value means better quality. Although the values are not directly comparable across compression types, this facilitates comparison of compression quality across images independent of compression mode.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.0  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *onboard_compression_rate*  
The onboard_compression_rate attribute provides the average number of bits needed to represent a pixel for image that was compressed on-board for data storage and transmission.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *onboard_compression_ratio*  
The onboard_compression_ratio attribute provides the ratio of the size, in bytes, of the original uncompressed data object to its compressed form (original size / compressed size). Onboard compression is performed for data storage and transmission.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *onboard_compression_type*  
The onboard_compression_type attribute identifies the type of on-board compression used for data storage and transmission. Valid Values: 'GZIP', 'ICER', 'H.264 Frame', 'LOCO', 'LZO', 'JPEG', 'JPEG Progressive', 'MSSS Lossless', 'Lossless', 'None', 'StarPixel Lossless', 'StarPixel Flexible', and 'Wavelet'.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - GZIP  
    - Description: GNU Gzip lossless compression using Lempel-Ziv coding (LZ77)  
  - H.264 Frame  
    - Description: Frame extracted from a video encoded using the H.264 codec  
  - ICER  
    - Description: ICER Adaptive Variable-Length Coding (ICER)  
  - ICT  
    - Description: Integer Cosine Transform  
  - JPEG  
    - Description: Joint Photographic Experts Group, an industry standard lossy compression algorithm.  
  - JPEG Progressive  
    - Description: interlaced progressive JPEG format, in which data is compressed in multiple passes of progressively higher detail.  
  - LOCO  
    - Description: Low-Complexity Lossless Compression  
  - LZO  
    - Description: Lempel-Ziv-Oberhumer, a type of lossless data compression focused on decompression speed.  
  - Lossless  
    - Description: Lossless compression method was used.  
  - MSSS Lossless  
    - Description: Lossless compression algorithm developed by Malin Space Science Systems.  
  - None  
    - Description: No on-board compression was used.  
  - StarPixel Flexible  
    - Description: StarPixel Flexible is a lossy hardware enabled compression, for example used for both Hayabusa2 ONC and TIR instruments. for more: https://www.mdpi.com/1424-8220/15/10/24926/htm  
  - StarPixel Lossless  
    - Description: StarPixel Lossless is a lossless hardware enabled compression, for example used for both Hayabusa2 ONC and TIR instruments. for more: https://www.mdpi.com/1424-8220/15/10/24926/htm  
  - Wavelet  
    - Description: Wavelet compression works by identifying repeating patterns in the content and representing them mathematically.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *onboard_compression_venue*  
 The onboard_compression_venue attribute specifies where the onboard compression was performed.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Hardware  
    - Description: Compression was applied on the hardward platform  
  - Software  
    - Description: Compression was applied in software  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *original_sample_bits*  
The original_sample_bits specifies the number of bits actually acquired by the sensor, before companding or other manipulations. Contrast this with img:sample_bits, which describes the current state of the image. Generally in a companded image, sample_bits will be less than original_sample_bits, while in a decompanded image they would be equal.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *out_of_focus_flag*  
A boolean value that denotes this image failed to find focus. Focus was commanded using autofocus or manual.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *output_dn*  
The output_dn attribute provides the value of the DN in the output image that is assigned to a given range of DN in the input image during companding.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *parameter_table_id*  
Specifies which table of parameters to use, or were used. Tables are defined in a mission- and instrument-specific manner.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *pixel_count*  
Integer number of pixels currently to list the total number of pixels as used in Hot_Pixel, Saturated_Pixel, and Nonlinear_Pixel classes.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *pixel_readout_time*  
Specifies the time between readout of each adjacent pixel. It is the time from the start of one pixel to the start of the next.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *pointing_model_name*  
The pointing_model_name attribute specifies which of several "pointing models" were used to transform the camera model based on updated pointing information. These updates are typically derived from mosaic seam corrections. This attribute and the associated Pointing_Model_Index classes define what the updated pointing information is, providing enough information to re-create the camera model from calibration data. If present, this attribute overrides the default pointing based on telemetry. The special value "NONE" shall be interpreted the same as if the attribute is absent (i.e. the default pointing model should be used). New model names can be created at any time; the models themselves should be described in a mission-specific ancillary file. See also the geom:solution_id attribute within the geom:Camera_Model_Parameters class.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *pointing_model_solution_id*  
The pointing_model_solution_id attribute specifies the identifier of the pointing correction solution used to derive the model specified via the enclosing Pointing_Correction class. This identifier should also appear in the pointing correction file referenced by the Data_Correction_File. If there is only one identifier in the correction file, then pointing_model_solution_id may be omitted. The pointing_model_solution_id attribute may be reused in the context of pointing corrections, although uniqueness is recommended. The pointing correction solution ID namespace is separate from the coordinate system namespace.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *pre_video_delay*  
pre_video_delay indicates the delay, generally in milliseconds or seconds, before the video starts.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *processing_algorithm*  
The processing_algorithm attribute specifies the name of the algorithm used to perform the processing specified by the enclosing class. Algorithm names should be defined in the project documentation, and/or in the enclosing class definition.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *processing_venue*  
The processing_venue attribute specifies where the processing described by the parent class was performed.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *product_flag*  
Indicates whether the product in the enclosing class was requested for downlink (when in Commanded_Parameters), or whether this product actually is the type in question (when in Imaging). For example, Commanded_Parameters.Histogram.product_flag = true indicates that a histogram was requested as part of the command that created the data product being labeled, while Imaging.Histogram.product_flag = true indicates that this data product itself is (or contains) a histogram.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *progressive_stage*  
In cases where each pass of a progressive JPEG is downlinked separately, the progressive_stage attribute indicates the highest pass number contained in this image, which indicates the available level of detail.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *r0*  
The r0 attribute specifies the 0th-order polynomial coefficient of the function used to describe an algorithmic flat field. See Radial_Flat_Field_Function for the formula.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *r1*  
The r1 attribute specifies the 1st-order polynomial coefficient of the function used to describe an algorithmic flat field. See Radial_Flat_Field_Function for the formula.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *r2*  
The r2 attribute specifies the 2nd-order polynomial coefficient of the function used to describe an algorithmic flat field. See Radial_Flat_Field_Function for the formula.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *r3*  
The r3 attribute specifies specifies the 3rd-order polynomial coefficient of the function used to describe an algorithmic flat field. See Radial_Flat_Field_Function for the formula.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *radiometric_type*  
The radiometric_type defines the specific type of radiance measurement. Possible values include "Radiance", "Radiance Factor", "Spectral Radiance", "Scaled Spectral Radiance", and "No CFA". Note: There are many more possible values, and this definition can be updated to include more examples over time.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - No CFA  
    - Description: Indicates the image is not and has never been CFA encoded. In this case, Color_Filter_Array would simply not be present in the label. This value is present in case it needs to be explicitly stated that there is no CFA.  
  - Radiance Factor  
    - Description: Radiance Factor also known as I/F or IOF. Some images are scaled to absolute radiance units, then divided by the absolute radiance of the Sun at the top of the planet's atmosphere to generate radiance factor, or "I over F" values, where I is the radiance from the surface (scene) and F is the radiance from the Sun at the top of the planet's atmosphere.  
  - Scaled Spectral Radiance  
    - Description: Radiometric correction results are expressed as Spectral Radiance, but have subsequently been scaled in some way to compensate for photometric effects (for example, adjusting the brightness as if the sun was at zenith or correcting for the impact of atmospheric opacity (tau)).  
  - Spectral Radiance  
    - Description: Radiometric correction results are expressed in units of Spectral Radiance (generally W/m^2/sr/nm).  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *radiometric_zenith_scaling_factor*  
Defines the scaling factor used for Scaled Radiance or Scaled Spectral Radiance. Scaled radiance is created by dividing radiance by this factor, which scales the radiance to what it would be if the sun were at the zenith with a clear atmosphere.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *raw_count*  
The raw_count attribute provides the value of some parameter measured by a spacecraft or instrument sensor in the raw units reported by that sensor. A separate attribute should be included alongside the raw_count that translates this value into the appropriate engineering units. i.e. temperature_value in degrees C or voltage_value in Volts  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *readout_direction_line*  
Specifies the direction in which lines are read from a camera. Directions are relative to the image as displayed (thus there may be an interaction with disp:Display_Direction).  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Bottom to Top  
    - Description: pixels are read bottom to top.  
  - Left to Right  
    - Description: pixels are read left to right.  
  - Right to Left  
    - Description: pixels are read right to left.  
  - Top to Bottom  
    - Description: pixels are read top to bottom.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *readout_direction_pixel*  
Specifies the direction in which adjacent pixels are read from a camera. Directions are relative to the image as displayed (thus there may be an interaction with disp:Display_Direction).  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Bottom to Top  
    - Description: pixels are read bottom to top.  
  - Left to Right  
    - Description: pixels are read left to right.  
  - Right to Left  
    - Description: pixels are read right to left.  
  - Top to Bottom  
    - Description: pixels are read top to bottom.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *readout_rate*  
The readout_rate attribute specifies the clock rate at which values are read from the sensor.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *responsivity_b*  
Specifies the conversion factor between DN and radiance units that has been applied to the blue channel of an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *responsivity_factor_b*  
Specifies the factor that has been applied to the B cell of the Bayer pattern, before de-Bayering (demosaicking) takes place.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *responsivity_factor_g*  
Specifies the factor that has been applied to the G cell of the Bayer pattern, before de-Bayering (demosaicking) takes place.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *responsivity_factor_r*  
Specifies the factor that has been applied to the R cell of the Bayer pattern, before de-Bayering (demosaicking) takes place.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *responsivity_g*  
Specifies the conversion factor between DN and radiance units that has been applied to the green channel of an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *responsivity_pan*  
Specifies the conversion factor between DN and radiance units that has been applied to a panchromatic image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *responsivity_r*  
Specifies the conversion factor between DN and radiance units that has been applied to the red channel of an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *responsivity_std*  
Specifies the 1-sigma standard deviation for the radiometric coefficients.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sample_bit_mask*  
The sample_bit_mask attribute Specifies the active bits in a sample. Any bit mask is valid in an non-raw product. Any 8-bit product, whether a scaled raw product or other, will have the value "2#11111111" and be stored in one byte. Any 12-bit product, whether an unscaled raw product, or an ILUT partially-processed product (see companding_method), will have the value "2#0000111111111111" and be stored in two bytes. A 15-bit product (e.g. Radiometrically-corrected Calibrated product type) will have the value "2#0111111111111111" and be stored in two bytes. Any 32-bit integer product (e.g. Histogram Raw product) will have the value "2#11111111111111111111111111111111" and be stored in four bytes. For floating-point data, sample_bit_mask is not valid and may be absent. If present, it should be ignored. NOTE: In the PDS, the domain of sample_bit_mask is dependent upon the currently-described value in the sample_bits attribute and only applies to unsigned integer values. Thus sample_bit_mask is not allowed for signed or floating-point types.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sample_bits*  
The sample_bits attribute specifies the logical or active number of bits in the data, which is distinct from the physical number of bits (for example, encoding 12-bit data within 16-bit words). These logical bits are stored in the low order (least significant) bits, with unused bits filled with 0 (or 1 for negative integers to preserve a two's complement representation). This is distinct from the valid data range (specified by valid_minimum and valid_maximum in Special_Constants class) because all values, including missing/invalid flag values, must fit within the sample_bits. The intent is that the data should be able to be sent through a communication channel that passes only sample_bits with no loss in fidelity.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sample_fov*  
The sample_fov attribute specifies the angular measure of the field of view of an imaged scene, as measured in the image sample direction (generally horizontal).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 360.0  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *samples*  
 The samples attribute indicates the total number of data instances along the horizontal axis of an image or sub-image.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- in [Image_Compression_Segment](#image_compression_segment):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Detector](#detector):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Subframe](#subframe):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *sampling_factor*  
 The sampling_factor attribute provides the value N, where every Nth data point was kept from the original data set by selection, averaging, or taking the median. When applied to an image object, the single value represented in sampling_factor applies to both the lines and the samples.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *saturated_flag*  
A boolean value that denotes that there exists pixels within the image that have reached or exceeded the maximum pixel value.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *saturated_pixel_count*  
The saturated_pixel_count attribute provides the number of pixels which were saturated. This can happen when the sensor acquired a value too low or too high to be measured accurately or if post-processing cause the output pixel value to fall below or above the the output range of valid values for the data or data type.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *segment_corrupted_flag*  
The segment_corrupted_flag specifies whether the segment is corrupted (or bad). Valid values are "true" or "false". If the value is true, the segment is corrupted, and if the value is false, the segment is not corrupted.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *segment_count*  
 The segment_count attribute identifies the number of segments into which the image was partitioned for error containment purposes.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *segment_number*  
 The segment_number attribute identifies which compression segment is described in the current Segment class.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *segment_quality*  
 The segment_quality attribute identifies the resultant or targeted image quality index for on-board ICER data compression. Upon return by the ICER decompress function, the output quantity segment_quality provides an indication of the quality of the reconstructed segment. Specifically, the value returned is a double for which the integer values correspond to attained min loss values, but in general is an interpolation between these values. Thus lower values of segment_quality correspond to higher reconstructed qualities, and a value of indicates lossless compression. Note that the compressed stream does not directly contain the value of min loss that was given to the compressor, but the decompressor does know how far along in the decompression process it got before it ran out of bits; this information is used to determine segment_quality. In rare circumstances the decompressor m ay not be able to determine segment_quality for a segment that it decompresses. In this case it sets segment_quality to 1.0. The reconstructed segment might be either lossy or lossless when this occurs. The technical condition under which a quality value is not determined is that the decompressor runs out of the data for the segment before decoding any bit plane information.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *segment_status*  
 The segment_status attribute provides a bit mask which provides the status of decoding for the compression segment identified by segment_number. Upon return by the ICER decompress function, the output quantity of segment_status contains a number indicating the decode status. The decode status may have one or more of the following flags set: SHORTDATASEG FLAG (bit 0): If this flag is set, then the segment contained so little data that nothing could be reconstructed in the segment. INCONSISTENTDATA FLAG (bit 1): If this flag is set, then one or more pieces of information in the segment header (specifically, image width, image height, n segs, wavelet filter, n decomps) are inconsistent with the value(s) in the first (valid) segment. ICER will ignore the data in this segment. DUPLICATESEG FLAG (bit 2): If this flag is set, then the segment index given in the header equals that given by a previous segment. The decompressor will ignore the data in this segment. BADBITPLANENUMBER FLAG (bit 3): If this flag is set, then an ICER internal parameter in the header for this segment has probably been corrupted. The decompressor will ignore the data in this segment. BADBITPLANECOUNT FLAG (bit 4): If this flag is set, then an ICER internal parameter in the header for this segment has probably been corrupted. The decompressor will ignore the data in this segment. BADDATA FLAG (bit 5): If this flag is set, then either the parameter combination given in the header for this segment are not allowed by ICER, or the segment number is bad. This probably indicates corrupted data. The decompressor will ignore the data in this segment.  
- PDS4 data type: ASCII_Numeric_Base2  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 6  
- Regex Pattern: [0-1]{1,255}  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sequence_number*  
The sequence_number attribute supplies the sequence identifier for the associated value in a group of related values.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Correction_Parameter](#correction_parameter):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [List_Index_No_Units_Imaging](#list_index_no_units_imaging--abstract)  `*abstract*`:  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Device_Component_State](#device_component_state):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Device_Current](#device_current):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Device_Motor_Count](#device_motor_count):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Device_Parameters](#device_parameters):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Device_Temperature](#device_temperature):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Device_Voltage](#device_voltage):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 3  
- in [Autoexposure](#autoexposure):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Brightness_Correction](#brightness_correction):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Color_Filter_Array](#color_filter_array):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Color_Processing](#color_processing):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Companding](#companding):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Dark_Current_Correction](#dark_current_correction):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Data_Processing](#data_processing):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Downsampling](#downsampling):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Flat_Field_Correction](#flat_field_correction):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Focus_Stack](#focus_stack):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [High_Dynamic_Range](#high_dynamic_range):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Image_Filter](#image_filter):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Image_Mask](#image_mask):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Radiometric_Correction](#radiometric_correction):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Shutter_Subtraction](#shutter_subtraction):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Spatial_Filter](#spatial_filter):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [White_Balance](#white_balance):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *sequence_terminated_flag*  
A boolean value that denotes that there exists pixels within the image that have reached or exceeded the maximum pixel value.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *shutter_subtraction_mode*  
The shutter_subtraction_mode specifies whether shutter subtraction will be performed, or if it is dependent on the exposure_duration_threshold_count.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Always  
    - Description: Always indicates the subtraction is, or will be, on regardless of other conditions  
  - Conditional  
    - Description: the exposure_duration_threshold_count will determine whether or not shutter subtraction will be performed  
  - None  
    - Description: shutter subtraction was not used  
  - True  
    - Description: shutter subtraction will be performed  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *shutter_type*  
Specifies the type of shutter the camera uses. "Global" exposes all pixels at the same time, so the image captures a consistent view of moving objects. "Rolling" scans across the scene, meaning each pixel is exposed at a slightly different time, which can introduce distortions for rapidly moving objects. This is generally a property of the camera itself and does not vary from frame to frame.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Global  
    - Description: shutter is of type global  
  - Rolling  
    - Description: shutter is of type rolling  
  - Unknown  
    - Description: shutter is of type unkown or not assigned  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *special_line*  
Line number of the special point.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *special_sample*  
Sample number of the special point.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *starpixel_degradation*  
 The value is degradation parameter. Then the value of the degradation parameter is higher, the quality of lossy compressed image will be worse, and the value is lower, the quality will be better. If value of degradation parameter is 0, there will be no degradation.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 32  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *starpixel_initial_subsampling_interval*  
 The value gives exponent n for initial subsampling interval 2**n. See Takada+2007 (https://doi.org/10.1109/IGARSS.2007.4422835) for the detail.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 8  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *striping_count*  
Specifies the number of stripes (N) used during dark current mitigation within image acquisition. Image "striping" is comprised of reading out the image in N different parts ("stripes"), often using a hardware windowing mode, using N separate exposures (with identical exposure times). These successive stripes correspond to physically different locations on the CCD. A commandable overlap (M rows) allows each successive row to "cover" the image pixels towards the readout region.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *striping_overlap_rows*  
Specifies the number of rows (M) of striping overlap used during dark current mitigation within image acquisition. Image "striping" is comprised of reading out the image in N different parts ("stripes"), often using a hardware windowing mode, using N separate exposures (with identical exposure times). These successive stripes correspond to physically different locations on the CCD. A commandable overlap (M rows) allows each successive row to "cover" the image pixels towards the readout region.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *subframe_type*  
 The subframe_type attribute specifies the method of subframing performed on the image. These methods may vary by mission so the permissible values should be set by the mission dictionaries. The current enumerations were added for the MSL mission and can be expanded if needed.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Hardware Compatible  
    - Description: Use hardware only if compatible.  
  - Hardware Else Software  
    - Description: Use hardware then software.  
  - None  
    - Description: No subframe requested.  
  - Software Only  
    - Description: Software processsing only.  
  - Subframe Around Sun  
    - Description: If the sun is found, send a subframed image of the sun. If sun is not found, send back no image.  
  - Sun Subframe Or Full  
    - Description: If the sun is found, send a subframed image of the sun. If the sun is not found, send back the entire image.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *temperature_status*  
The temperature_status attribute defines the status of the associated temperature measurement. The status is interpreted in a device-specific way, but generally 0 indicates a successful measurement.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *temperature_value*  
The temperature_value attribute provides the temperature, in the specified units, of some point on an imaging instrument or other imaging instrument device.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: Yes  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *threshold_factor*  
Multiplicative factor used to isolate pixels that are X times greater than theie nearest neighbors.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *threshold_value*  
Value used to define a level that triggers a defined behavior.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tile_count*  
Defines the number of tiles in this set. Should be present and equal to the number of Tile objects if Tile is used; optional if Tile is not used.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tile_lines*  
Defines the number of lines in a regular tile. Not used for irregular tiles.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tile_num_bands*  
Specified the number of bands for this tile. The tile number of bands may not match the number of bands for the overall image, in which case it reflects the number of bands the original tile had before assembly, or the number of bands the tile should have after disassembly.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tile_number*  
Specifies the tile number (array index), starting at 1.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *tile_samples*  
Defines the number of samples in a regular tile. Not used for irregular tiles.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 1  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tile_type*  
Defines the type of tiles. Regular tiles are the same size throughout (although the last row or column of tiles might be smaller in order to fit the image size) and should have tile_lines and tile_samples defined. Irregular tiles may have different sizes per tile, described in each Tile class.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Irregular  
    - Description: tiles sizes are not regular or the same size throughout  
  - Regular  
    - Description: tiles sizes are the same size thorughout.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tile_upsample_method*  
Specifies how tiles were upsampled (if needed) to create the full image. Replication simply repeats the pixel value as many times as necessary, Bilinear is bilinear interpolation, and None means upsampling was not necessary.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Bilinear  
    - Description: Bilinear interpolation  
  - None  
    - Description: None means upsampling was not necessary  
  - Replication  
    - Description: Replication simply repeats the pixel value as many times as necessary  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tile_venue*  
Specifies where the tiling was done. Generally, Onboard indicates that this image is a reassembly of tiles sent from the spacecraft, while Ground indicates a tile decomposition after processing.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Ground  
    - Description: Ground indicates a tile decomposition after processing  
  - Onboard  
    - Description: Onboard indicates that this image is a reassembly of tiles sent from the spacecraft  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *valid_maximum_pixel*  
Specifies the maximum pixel DN value for pixels used by the autoexposure algorithm.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *valid_minimum_pixel*  
Specifies the minimum DN threshold for pixels used by the autoexposure algorithm.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *valid_pixel_count*  
The valid_pixel_count attribute provides the total number of pixels tagged as valid. This will generally not include pixels flagged as saturated_pixel_count or missing_pixel_count.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *value*  
The value attribute provides a single, allowed numerical or character string value.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *value_number*  
The value_number attribute provides the value with no applicable units as named by the associated id, name, or sequence_number.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *value_string*  
The value_string attribute provides the value with no applicable units as named by the associated id, name, or sequence_number.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *video_flag*  
 The video_flag attribute indicates whether or not video products were commanded.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *voltage_value*  
The voltage_value attribute provides provides the voltage, in the specified units, of an imaging instrument or some part of the imaging instrument.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *wavelet_filter*  
The wavelet_filter attribute specifies the filter used in the compression and decompression algorithm.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *white_balance_color_temp*  
The color temperature used to white-balance the image generally reported in Kelvin. For example, on Earth 5000-6500K might be set when there are clear skies with the sun overhead.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *width_pixels*  
The width_pixels attribute provides the horizontal dimension, in pixels.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *wrong_filter_flag*  
A boolean value that denotes the commanded filter does not match the actual filter used to acquire the image.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *wrong_pointing_flag*  
A boolean value that denotes this image has the wrong pointing as pre-determined through planned observations or image footprints. For example, the rover faulted while driving and did not make it to the intended location and therefore the images have the wrong pointing.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *wrong_zoom_flag*  
A boolean value that denotes the commanded zoom does not match the actual zoom value. For example, commanded at 110mm but acquired at 63mm.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *x_center*  
The x_center attribute specifies the sample coordinate of the center of the function used to describe an algorithmic flat field. See Radial_Flat_Field_Function for the formula.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *y_center*  
The y_center attribute specifies the line coordinate of the center of the function used to describe an algorithmic flat field. See Radial_Flat_Field_Function for the formula.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *zero_value_pixels_flag*  
A boolean value that denotes this image has pixels with a DN value of zero.  
- PDS4 data type: ASCII_Boolean  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *zoom_position*  
The zoom_position attribute defined, in a camera-specific way, the zoom metric that should be used for geometric processing of the data (e.g. for creating camera models). This will often be the zoom motor count.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
# Examples  
  
# Edit History  
*See also: [IMG change log](https://github.com/pds-data-dictionaries/ldd-img/blob/main/CHANGELOG.md).*  
2025-05-12  Trent Hare
