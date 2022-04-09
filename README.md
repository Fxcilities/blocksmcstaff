# staff detection

```java
    String server = "blocksmc"; // OPTIONS: blocksmc, vipermc
    List<String> blocksMcStaff = getList("https://raw.githubusercontent.com/Fxcilities/blocksmcstaff/main/" + server + ".txt");

    /**
     * @author Fxcilities
     */
    public static List<String> getList(String rawUrl) throws IOException {
        List<String> result = new ArrayList<>();

        URL url = new URL(rawUrl);
        URLConnection conn = url.openConnection();
        BufferedReader in = new BufferedReader(
                new InputStreamReader(
                        conn.getInputStream()));
        String inputLine;
        while ((inputLine = in.readLine()) != null) {
            inputLine = inputLine.replace("\n", "");
            if (inputLine.startsWith("#") || inputLine.equals("")) continue;
            result.add(inputLine);
        }

        in.close();
        return result;
    }
```
