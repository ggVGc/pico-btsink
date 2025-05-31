cmake_minimum_required(VERSION 3.12)

if (PICO_CYW43_SUPPORTED) # set by PICO_BOARD=pico_w
    if (NOT TARGET pico_cyw43_arch)
        message("Skipping Pico W examples as support is not available")
    else()
        if (NOT TARGET pico_btstack_base)
            message("Skipping Pico W Bluetooth examples as support is not available")
        else()
            add_subdirectory(bt)
        endif()
    endif()
endif()
