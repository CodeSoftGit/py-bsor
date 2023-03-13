# BS Open Replay Python parser

[Beat Saber Open Replay format](https://github.com/BeatLeader/BS-Open-Replay) parser written in Python

## Usage
```sh
pip install py_bsor
```

```python
from bsor.Bsor import make_bsor
from bsor.Scoring import calc_score
import os

if __name__ == '__main__':
    filename = 'D:/something/easy.bsor'
    print('File name :    ', os.path.basename(filename))
    try:
      with open(filename, 'rb') as f:
          m = make_bsor(f)
          print('BSOR Version: %d' % m.file_version)
          print('BSOR notes: %d' % len(m.notes))
          print(m.info)
          stats = calc_score(m)
          print(stats)
    except BSException as e:
      raise
