add_library(a2dp_sink_demo_pins INTERFACE)
target_compile_definitions(a2dp_sink_demo_pins INTERFACE
      USE_AUDIO_I2S=1
      PICO_AUDIO_I2S_DATA_PIN=18
      PICO_AUDIO_I2S_CLOCK_PIN_BASE=16
    )


picow_bt_example_target_name(a2dp_sink_demo TARGET_NAME)
picow_bt_example_background(a2dp_sink_demo ${TARGET_NAME} pico_btstack_sbc_decoder picow_bt_example_no_cyw43_lwip_background pico_btstack_ble pico_btstack_classic ${ARGN})

target_sources(picow_bt_example_common_a2dp_sink_demo INTERFACE
  ${CMAKE_CURRENT_LIST_DIR}/main.c
)
