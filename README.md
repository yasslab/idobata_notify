# Idobata Notify - GitHub Action

A [GitHub Action](https://github.com/features/actions) to send CI result to a Idobata channel. :bell:

![Idobata Notify examples](https://user-images.githubusercontent.com/155807/135367296-95b223db-0040-4560-8d32-20bff5c97839.png)

<br>

## How to use

```
# Single job use

  - name: 🔔 Notify results
    uses: yasslab/idobata_notify
    if: always()
    with:
      idobata_hook_url: ${{ secrets.IDOBATA_GITHUB_ACTIONS }}
```

```
# Matrix

  notify:
    needs: test # depends where the matrix job is located
    runs-on: ubuntu-latest
    if: always()
    steps:

      - name: 🔔 Notify results
        uses: yasslab/idobata_notify
        with:
          idobata_hook_url: ${{ secrets.IDOBATA_GITHUB_ACTIONS }}
          status: ${{ needs.test.result }} # passing the matrix jobs results
```

## LICENSE

MIT License. https://github.com/yasslab/idobata_notify/blob/main/LICENSE

<br>

## Copyright

Copyright &copy; [YassLab Inc.](https://yasslab.jp) 2012-2021

[![YassLab 株式会社ロゴ](https://yasslab.jp/img/logos/800x200.png?cache=clear)](https://yasslab.jp/)
