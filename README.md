# oj-resolve-action
Action for `competitive-verifier oj-resolve`.

See [action.yml](action.yml) or [competitive-verifier/competitive-verifier](https://github.com/competitive-verifier/competitive-verifier).

## Example

```yml
      # include & exclude
      - name: oj-resolve
        uses: competitive-verifier/oj-resolve-action@v1
        with:
          output-path: ./verify.json
          include: |
            src
            others
          exclude: |
            src/resource
            others/tests

      # Resolve from all file
      - name: oj-resolve
        id: resolve
        uses: competitive-verifier/oj-resolve-action@v1
        with:
          output-path: ./verify-all.json

      - name: Use resolved json
        run: |
          echo "${{ steps.resolve.outputs.json-path }}"
          test "${{ steps.resolve.outputs.json-path }}" = "./verify-all.json"
```