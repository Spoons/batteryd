# batteryd - Battery Notification Daemon

A simple customizable daemon that notifies you to plug in your laptop. Single low battery notifications are easy to miss, ignore, and forget. Batteryd is far more persistent out of the box and can be configured to any level of persistence desired.

  - Written in Python with no external dependencies.

## Dependencies

  - Python 3.4+

## Installation

### Arch Linux
```
git clone https://github.com/Spoons/batteryd.git batteryd
cd batteryd
makepkg -si
systemctl --user daemon-reload
systemctl --user enable --now batteryd
systemctl --user status batteryd
```
### Other Distributions
```
git clone https://github.com/Spoons/batteryd.git batteryd
cd batteryd
install -Dm 755 batteryd -t /usr/local/bin/
install -Dm 644 batteryd.service -t ~/.config/systemd/user/
systemctl --user daemon-reload
systemctl --user enable --now batteryd
systemctl --user status batteryd
```

## Configuration

Edit the warnings, poll_short, poll_long, and poll_duration_decrease_offset variables in the script to achieve the desired intensity. batteryd will send a notification off for every 'percent' indicated by the warnings list.

For example, to send a notification at 30% and a persistent warning between 10%-20%, use the snippet below.

```
warnings = [ 30 ] + list(range(10, 20))
```


## Usage

Run the script directly `./batteryd` or start it from the systemd unit.

## Getting help

Post issues on the tracker.

## License

GPLv3
