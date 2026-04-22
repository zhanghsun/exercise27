<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Responsive Layout</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 24px;
      background: #efefef;
      font-family: Arial, Helvetica, sans-serif;
    }

    .outer {
      width: min(760px, 100%);
      background: #55acec;
      padding: 18px;
    }

    .panel {
      width: min(360px, 100%);
      margin: 0 auto;
      background: #ffffff;
      border-radius: 12px;
      padding: 12px;
    }

    .layout {
      display: grid;
      gap: 6px;
      grid-template-columns: 1fr 1fr;
      grid-template-areas:
        "header header"
        "main1 main1"
        "main2 main2"
        "main3 main3"
        "foot1 foot2"
        "foot3 foot4";
    }

    .box {
      width: 100%;
      border-radius: 2px;
    }

    .header {
      grid-area: header;
      background: #a9cf45;
      height: 110px;
    }

    .main {
      background: #18b8cc;
      height: 46px;
    }

    .main1 { grid-area: main1; }
    .main2 { grid-area: main2; }
    .main3 { grid-area: main3; }

    .footer {
      background: #d6dde1;
      height: 34px;
    }

    .foot1 { grid-area: foot1; }
    .foot2 { grid-area: foot2; }
    .foot3 { grid-area: foot3; }
    .foot4 { grid-area: foot4; }

    @media (min-width: 480px) {
      .panel {
        width: min(520px, 100%);
      }

      .layout {
        grid-template-columns: repeat(12, 1fr);
        grid-template-areas: none;
      }

      .header {
        grid-column: 1 / 13;
        grid-row: 1;
        height: 120px;
      }

      .main1 {
        grid-column: 1 / 5;
        grid-row: 2;
      }

      .main2 {
        grid-column: 5 / 9;
        grid-row: 2;
      }

      .main3 {
        grid-column: 9 / 13;
        grid-row: 2;
      }

      .main {
        height: 132px;
      }

      .foot1 {
        grid-column: 1 / 4;
        grid-row: 3;
      }

      .foot2 {
        grid-column: 4 / 7;
        grid-row: 3;
      }

      .foot3 {
        grid-column: 7 / 10;
        grid-row: 3;
      }

      .foot4 {
        grid-column: 10 / 13;
        grid-row: 3;
      }

      .footer {
        height: 76px;
      }
    }
  </style>
</head>
<body>
  <div class="outer">
    <div class="panel">
      <div class="layout">
        <div class="box header"></div>
        <div class="box main main1"></div>
        <div class="box main main2"></div>
        <div class="box main main3"></div>
        <div class="box footer foot1"></div>
        <div class="box footer foot2"></div>
        <div class="box footer foot3"></div>
        <div class="box footer foot4"></div>
      </div>
    </div>
  </div>
</body>
</html>
