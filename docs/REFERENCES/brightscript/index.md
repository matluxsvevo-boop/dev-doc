sub OnSongFocused()
    song = m.songList.content.getChild(m.songList.itemFocused)

    announcement = song.title + " by " + song.artist

    m.top.signalBeacon("AccessibilityAnnouncement", {
        message: announcement
    })
end sub

sub ReadSongInfo(songTitle as String, artist as String)
    message = "Now playing " + songTitle + " by " + artist

    screen = CreateObject("roSGNode", "Label")
    screen.text = message

    ' Accessibility announcement
    m.top.signalBeacon("AccessibilityAnnouncement", {
        message: message
    })
end sub
