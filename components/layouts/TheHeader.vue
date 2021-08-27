<template>
  <header id="header" class="TheHeader">
    <div class="inner">
      <div class="header-cont">
        <!-- 로그인 체크 필요 -->
        <h1 class="logo">
          <nuxt-link :to="`${loginCheckUrl}`"><img src="/images/logo-soldout-black.svg" alt="soldout"></nuxt-link>
        </h1>
        <!-- 검색 영역 - 검색 버튼 클릭 시 검색 결과 노출 -->
        <div v-if="loginCheck" class="search-form-box">
          <div class="search-form">
            <button
                @click="searchSubmit"
                type="button" class="btn-search" aria-label="검색 버튼" />
            <label class="header-search-label" for="header-search">검색창</label>
            <input
                  @keyup.enter="searchSubmit"
                  @input="searchInput"
                  :value="searchWord"
                  type="text" id="header-search" class="header-search" name="header-search" placeholder="제품명, 모델번호, 브랜드명 등">
            <button
                  v-if="searchWord"
                  @click="searchDelete"
                  type="button" class="btn-search-del" aria-label="검색어 삭제" />
          </div>
          <button
                v-if="searchWord"
                @click="searchDelete"
                type="button" class="txt-search-del">취소</button>
        </div>
        <div v-if="loginCheck" class="sub-menu">
          <ul class="sub-menu-list">
            <li><nuxt-link to="/mypage">마이페이지</nuxt-link></li>
            <!-- [로그아웃] 클릭 시 로그아웃 처리되며 로그인 페이지로 이동 -->
            <li><a href="">로그아웃</a></li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      loginCheck : true,
      searchWord : '',
    }
  },
  computed: {
    loginCheckUrl(){
      // 추후 로그인 체크값 전달 받아 처리
      if(this.loginCheck){
        return '/product/list'
      } else{
        return '/user/login'
      }
    }
  },
  methods: {
    searchInput(e){
      this.searchWord = e.target.value
    },
    searchDelete(){
      this.searchWord = ''
    },
    searchSubmit(){
      console.log('검색어 입력');
      this.searchWord = ''
    }
  },
}
</script>

<style lang="scss" scoped>
  .TheHeader{
    .header-cont{
      display: flex;
      flex-wrap: nowrap;
      justify-content: space-between;
      align-items : center;
      height: 94px;
      .logo{
        width: 132px;
        height: 30px;
        > a{
          display: block;
          line-height: 0;
        }
      }
      .search-form-box{
        display: flex;
        min-width: 648px;
        .search-form{
          overflow: hidden;
          display: flex;
          justify-content: space-between;
          align-items: center;
          width: 600px;
          height: 44px;
          padding: 0 12px;
          border-radius: 8px;
          background: $Gray20;
          .btn-search{
            flex: 0 0 20px;
            display: block;
            height: 20px;
            font-size: 0;
            text-indent: -9999px;
            background: url('/images/ic-20-common-search.svg') no-repeat center center / 100%;
          }
          .header-search-label{
            @include skip();
          }
          .header-search{
            width: 100%;
            height: 23px;
            margin: 0 20px 0 10px;
            border: 0;
            font-size: 14px;
            color: $Black;
            background: transparent;
          }
          .btn-search-del{
            flex: 0 0 20px;
            display: block;
            height: 20px;
            font-size: 0;
            text-indent: -9999px;
            background: url('/images/ic-20-input-delete.svg') no-repeat center center / 100%;
          }
        }
        .txt-search-del{
          margin-left: 20px;
          font-size: 16px;
          color:$Black;
        }
      }
      .sub-menu{
        .sub-menu-list{
          @include clearfix();
          > li{
            float: left;
            margin-left: 20px;
            &:first-child{
              margin-left: 0;
            }
            > a{
              display: block;
              font-size: 13px;
              color: $Gray70;
            }
          }
        }
      }
    }
  }
</style>

