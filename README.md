

rp-radio i pma-voice

pod item
 
radio ma zrobione kanały prywatne np dla policji itp
 
1. instalacja 

do server cfg dodaj 

#---voip---#
setr voice_useSendingRangeOnly true
setr voice_useNativeAudio true
setr voice_enableUi 0
setr voice_enableRadios 1
setr voice_enablePhones 1
setr voice_enableRadioAnim 1
setr voice_defaultRadio "M"
setr voice_defaultCycle "F5"
setr voice_defaultVolume "1.0"
setr voice_enableSubmix 1
setr voice_defaultRadioVolume 60
setr voice_defaultPhoneVolume 70

start pma-voice
start rp-radio
#--voip--#

2. wpierdol sql do bazy 

4. jak podpiąć hud  do pma wklej tą funkcję a starą usuń 

!!! to jest przykładowa funkcja więc nie pomagam na pv !!!



CreateThread(function()
    while true do
        Wait(400)
        local state = NetworkIsPlayerTalking(PlayerId())
        local mode = Player(GetPlayerServerId(PlayerId())).state.proximity.mode
        SendNUIMessage({
            type = 'UPDATE_VOICE',
            isTalking = state,
            mode = mode
        })
    end
end)


xarm.xyz nyfrus#2322 pozdrawia
