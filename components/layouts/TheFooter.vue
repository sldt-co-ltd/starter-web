<template>
  <footer id="footer" class="TheFooter">
    <div class="inner">
      <div class="footer-info">
        <h3 class="title">(주) 에스엘디티</h3>
        <div class="info-list-box">
          <ul class="info-list">
            <li>주식회사 에스엘디티 : SLDT Co., Ltd.</li>
            <li>대표이사 : 한문일</li>
            <li>사업자등록번호: 113-86-12510 <a href="https://www.ftc.go.kr/bizCommPop.do?wrkr_no=1138612510&apv_perm_no=ftc.go.krftc.go.kr" target="_blank" title="새창 열기">사업자정보</a></li>
            <li>사업장소재지: 서울특별시 강남구 테헤란로 413, 5층</li>
            <li>검수센터: 서울특별시 성동구 아차산로 126 지하 2층 솔드아웃 검수센터</li>
            <li>호스팅 서비스: 마이크로소프트</li>
          </ul>
        </div>
        <p class="info-txt">
          주식회사 에스엘디티는 통신판매 중개자로서 통신판매의 당사자가 아니므로 개별판매자가 등록한 상품정보에 대해서 책임지지 않습니다. <br />
          단, 거래과정에서 검수하고 보증하는 내용에 대한 책임은 당사에 있습니다.
        </p>
      </div>
      <div class="footer-cs">
        <h3 class="title">솔드아웃 고객센터</h3>
        <div class="cs-box">
          <a class="cs-email" href="mailto:support@soldout.co.kr">support@soldout.co.kr</a>
          <p class="txt">1:1 문의는 솔드아웃 앱 > 마이 페이지에서 가능합니다.</p>
          <p class="time">(평일 11시~18시 / 점심13시~14시)</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
  .TheFooter{
    border-top: 1px solid $Gray25;
    .inner{
      display: flex;
      flex-wrap: nowrap;
      justify-content: space-between;
      padding: 40px 0 58px;
    }
    .title{
      font-family: map-get($TEXT_FONT_STACK, 'musinsa');
      font-size: 16px;
      font-weight: 500;
    }
    .footer-info{
      overflow: hidden;
      flex: 0 0 785px;
      .info-list-box{
        padding: 18px 0 16px;
        border-bottom: 1px solid $Gray25;
        .info-list{
          @include clearfix();
          margin-left: -12px;
          > li{
            float: left;
            margin-left: 12px;
            font-size: 12px;
            line-height:18px;
            color: $Gray70;
            >a{
              text-decoration: underline;
            }
          }
        }
      }
      .info-txt{
        margin-top: 18px;
        font-size: 12px;
        line-height: 20px;
        color: #bbb;
      }
    }
    .footer-cs{
      .cs-box{
        margin-top: 20px;
        font-size: 12px;
        .cs-email{
          color: $Gray70;
          text-decoration: underline;
        }
        .txt{
          margin-top: 14px;
          font-weight: 700;
        }
        .time{
          margin-top: 8px;
          color: #bbb;
        }
      }
    }
  }
</style>

