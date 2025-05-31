picow_bt_example_target_name(pico-bt-dac TARGET_NAME)
picow_bt_example_background(pico-bt-dac ${TARGET_NAME} pico_btstack_sbc_decoder picow_bt_example_no_cyw43_lwip_background pico_btstack_ble pico_btstack_classic ${ARGN})

target_compile_definitions(picow_bt_example_common_pico-bt-dac INTERFACE
      USE_AUDIO_I2S=1
      PICO_AUDIO_I2S_DATA_PIN=18
      PICO_AUDIO_I2S_CLOCK_PIN_BASE=16
    )

target_sources(picow_bt_example_common_pico-bt-dac INTERFACE
  ${CMAKE_CURRENT_LIST_DIR}/main.cpp
)
