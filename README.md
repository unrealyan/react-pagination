# react-pagination
Pagination
demo

 queryFunc(pageSize,currentPage){
        const {shouldPaymentInfoListQueryFields,setShouldPaymentInfoList}=this.props;
        let formFields={
            status: shouldPaymentInfoListQueryFields.status,
            startDate: shouldPaymentInfoListQueryFields.startDate,
            endDate: shouldPaymentInfoListQueryFields.endDate,
            _paged: true,
            _pageNo: currentPage-1,
            _pageSize: pageSize
        };
        console.log(shouldPaymentInfoListQueryFields)
        // const {getListDetail}=this.props;
        restClient.getManager(SecurityService.getScopeKey(), 'RepaymentPlanInfoDto')
            .query('findRepaymentList', formFields)
            .then((rsp)=>{
                console.log(rsp)
                setShouldPaymentInfoList(rsp)
            });
        setLocation(formFields)
    }



 <Pagination  pageCount={detailPageNum} queryFunc={this.queryFunc.bind(this)}/>
