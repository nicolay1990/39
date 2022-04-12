```
iptables -I FORWARD 1 -m string --algo bm --string "BitTorrent" -j DROP iptables -I FORWARD 1 -m string --algo bm --string "BitTorrent protocol" -j DROP iptables -I FORWARD 1 -m string --algo bm --string "peer_id=" -j DROP iptables -I FORWARD 1 -m string --algo bm --string ".torrent" -j DROP iptables -I FORWARD 1 -m string --algo bm --string "announce.php?passkey=" -j DROP iptables -I FORWARD 1 -m string --algo bm --string "torrent" -j DROP iptables -I FORWARD 1 -m string --algo bm --string "announce" -j DROP iptables -I FORWARD 1 -m string --algo bm --string "info_hash" -j DROP
```

```
ip6tables -I FORWARD 1 -m string --algo bm --string "BitTorrent" -j DROP ip6tables -I FORWARD 1 -m string --algo bm --string "BitTorrent protocol" -j DROP ip6tables -I FORWARD 1 -m string --algo bm --string "peer_id=" -j DROP ip6tables -I FORWARD 1 -m string --algo bm --string ".torrent" -j DROP ip6tables -I FORWARD 1 -m string --algo bm --string "announce.php?passkey=" -j DROP ip6tables -I FORWARD 1 -m string --algo bm --string "torrent" -j DROP ip6tables -I FORWARD 1 -m string --algo bm --string "announce" -j DROP ip6tables -I FORWARD 1 -m string --algo bm --string "info_hash" -j DROP
```